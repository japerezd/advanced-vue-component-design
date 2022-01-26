<template>
  <span
    class="toggle flex-no-shrink"
    role="checkbox"
    tabindex="0"
    :aria-checked="toggled.toString()"
    @click="toggleNewsletter"
    @keydown.space.prevent="toggleNewsletter"
  >
  </span>
</template>

<script>
export default {
model: {
    prop: 'toggled',
    event: 'toggle'
},
  props: ['toggled'],
  methods: {
    toggleNewsletter() {
      this.$emit('toggle', !this.toggled);
    },
  },
};
</script>

<style></style>
