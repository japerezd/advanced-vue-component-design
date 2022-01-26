<template>
  <button
    type="button"
    class="text-red-dark hover:underline"
    @click="confirmDeleteModalOpen = true"
  >
    Delete Account
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
import ConfirmDeleteModal from './ConfirmDeleteModal.vue';

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
