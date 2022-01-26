<template>
  <with-dimensions #default="{ width }">
    <div
      class="profile-card"
      :class="{ 'profile-card--horizontal': width >= 400 }"
    >
      <img
        class="profile-card-image"
        src="https://uploads.codesandbox.io/uploads/user/442f24f7-c646-47f4-9e78-00d4d01b35a9/OwRL-toby.jpg"
      />
      <div class="profile-card-meta">
        <div class="mb-4">
          <p class="text-xl leading-tight">Toby Flenderson</p>
          <p class="text-sm leading-tight text-grey-dark">
            Human Resources at Duner Mifflin
          </p>
        </div>
        <div>
          <button class="btn btn-sm btn-pill btn-indigo-outline">
            Message
          </button>
        </div>
      </div>
    </div>
  </with-dimensions>
</template>

<script>
import WithDimensions from './WithDimensions.vue';

export default {
  components: { WithDimensions },
};
</script>

<style></style>
