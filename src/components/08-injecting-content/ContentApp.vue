<template>
  <div class="min-h-screen bg-grey-lighter p-8">
      <div class="text-center p-8 my-8">
          <primary-button>
              <svg xmlns="http://www.w3.org/2000/svg" width="192" height="192" fill="#000000" viewBox="0 0 256 256"><rect width="256" height="256" fill="none"></rect><polyline points="86 110 128 152 170 110" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline><line x1="128" y1="40" x2="128" y2="152" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line><path d="M216,152v56a8,8,0,0,1-8,8H48a8,8,0,0,1-8-8V152" fill="none" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></path></svg>
              Download
          </primary-button>
      </div>

      <div class="max-w-xs mx-auto mb-8">
          <media-card>
              <img slot="image" src="https://images.unsplash.com/photo-1638913660695-b490171d17c9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1472&q=80" alt="s">
              <template slot="heading">
                  The Long Road to Mastering the Perfect Cartwheel
              </template>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim aperiam error assumenda voluptatem veniam quo nam deleniti incidunt similique vel sunt, vitae quae ipsum consequuntur? A quia molestias quas pariatur.</p>
          </media-card>
      </div>
      <modal></modal>
  </div>
</template>

<script>
import PrimaryButton from './PrimaryButton.vue';
import MediaCard from './MediaCard.vue';
import Modal from './Modal.vue';

export default {
    components: {
        PrimaryButton,
        MediaCard,
        Modal
    }
}
</script>

<style>

</style>