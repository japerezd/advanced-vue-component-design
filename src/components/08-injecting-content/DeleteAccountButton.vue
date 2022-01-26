<template>
  <button
    type="button"
    @click="confirmDeleteModalOpen = true"
  >
    <slot></slot>
    <portal to="modals">
      <confirm-delete-modal
        :show="confirmDeleteModalOpen"
        :account-id="accountId"
        @close="confirmDeleteModalOpen = false"
      ></confirm-delete-modal>
    </portal>
  </button>
</template>

<script>
import ConfirmDeleteModal from '@/components/06-portals/ConfirmDeleteModal.vue';

export default {
  components: {
    ConfirmDeleteModal,
  },
  props: ['accountId'],
  data() {
    return {
      confirmDeleteModalOpen: false,
    };
  },
};
</script>

<style></style>
