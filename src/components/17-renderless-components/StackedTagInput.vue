<template>
  <!-- V-model no funciona (muta el prop value). Se usa :Value e @input, en este caso los que estan definidos
como modelo en RenderlessTagInput -->
  <renderless-tag-input
    :tags="tags"
    :remove-on-backspace="false"
    @update="(newTags) => $emit('update', newTags)"
    #default="{
      tags: newTags,
      addTag,
      removeButtonEvents,
      inputProps,
      inputEvents,
    }"
  >
    <div class="stacked-tag-input">
      <div class="stacked-tag-input-form">
        <input
          type="text"
          class="form-input"
          placeholder="Add tag..."
          v-bind="inputProps"
          v-on="inputEvents"
        />
        <button class="btn btn-indigo" @click="addTag">Add Tag</button>
      </div>

      <ul class="stacked-tag-list">
        <li v-for="tag in newTags" :key="tag">
          {{ tag }}
          <button
            type="button"
            class="stacked-tag-link"
            v-on="removeButtonEvents(tag)"
          >
            Remove
          </button>
        </li>
      </ul>
    </div>
  </renderless-tag-input>
</template>

<script>
import RenderlessTagInput from './RenderlessTagInput.vue';

export default {
  components: {
    RenderlessTagInput,
  },
  model: {
    prop: 'tags',
    event: 'update',
  },

  props: {
    tags: { required: true },
  },
};
</script>

<style></style>
