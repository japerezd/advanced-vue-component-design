<template>
  <on-click-outside :do="close">
    <div class="search-select" :class="{ 'is-active': isOpen }">
      <button
        ref="button"
        @click="open"
        type="button"
        class="search-select-input"
      >
        <span v-if="value !== null">{{ value }}</span>
        <span v-else class="search-select-placeholder">Select a band...</span>
      </button>
      <div ref="dropdown" v-show="isOpen" class="search-select-dropdown">
        <input
          ref="search"
          v-model="search"
          type="text"
          class="search-select-search"
          @keydown.esc="close"
          @keydown.up="highlightPrev"
          @keydown.down="highlightNext"
          @keydown.enter.prevent="selectHighlighted"
          @keydown.tab.prevent
        />
        <ul
          ref="options"
          v-show="filteredOptions.length"
          class="search-select-options"
        >
          <li
            class="search-select-option"
            :class="{ 'is-active': i === highlightedIndex }"
            v-for="(option, i) in filteredOptions"
            :key="option"
            @click="select(option)"
          >
            {{ option }}
          </li>
        </ul>
        <div v-show="!filteredOptions.length" class="search-select-empty">
          No results found for "{{ search }}"
        </div>
      </div>
    </div>
  </on-click-outside>
</template>

<script>
import OnClickOutside from './OnClickOutside.vue';
import Popper from 'popper.js';

export default {
  props: ['value', 'options', 'filterFunction'],
  components: { OnClickOutside },
  data() {
    return {
      isOpen: false,
      search: '',
      highlightedIndex: 0,
    };
  },

  beforeDestroy() {
    this.popper.destroy();
  },

  computed: {
    filteredOptions() {
      return this.filterFunction(this.search, this.options);
    },
  },

  methods: {
    open() {
      if (this.isOpen) {
        return;
      }
      this.isOpen = true;
      this.$nextTick(() => {
        this.setupPopper();
        this.$refs.search.focus();
        this.scrollToHighlighted();
      });
    },

    setupPopper() {
      if (this.popper === undefined) {
        this.popper = new Popper(this.$refs.button, this.$refs.dropdown, {
          placement: 'bottom',
        });
      } else {
        this.popper.scheduleUpdate();
      }
    },

    close() {
      if (!this.isOpen) {
        return;
      }
      this.isOpen = false;
      this.$refs.button.focus();
    },

    select(option) {
      // this.value = option;
      this.$emit('input', option);
      this.search = '';
      this.highlightedIndex = 0;
      this.close();
    },

    selectHighlighted() {
      this.select(this.filteredOptions[this.highlightedIndex]);
    },

    scrollToHighlighted() {
      this.$refs.options.children[this.highlightedIndex].scrollIntoView({
        block: 'nearest',
      });
    },

    highlight(index) {
      this.highlightedIndex = index;

      if (this.highlightedIndex < 0) {
        this.highlightedIndex = this.filteredOptions.length - 1;
      }

      if (this.highlightedIndex > this.filteredOptions.length - 1) {
        this.highlightedIndex = 0;
      }

      this.scrollToHighlighted();
    },

    highlightPrev() {
      this.highlight(this.highlightedIndex - 1);
    },

    highlightNext() {
      this.highlight(this.highlightedIndex + 1);
    },
  },
};
</script>
