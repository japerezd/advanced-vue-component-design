<template>
  <div class="min-h-screen bg-grey-darker p-8">
    <div class="max-w-md mx-auto mb-8">
      <fetch-json v-slot="{ json: albums, loading }" url="/albums.json">
        <div class="card">
          <h1 class="text-2xl font-bold mb-6">Top Death Metal Albums</h1>
          <div v-if="loading">Loading...</div>
          <div v-else class="album-grid">
            <div
              class="album-grid-item"
              v-for="album in albums"
              :key="album.id"
            >
              <img :src="album.artwork" :alt="album.title" />
              <h2 class="album-title">{{ album.title }}</h2>
              <p class="album-artist">{{ album.artist }}</p>
            </div>
          </div>
        </div>
      </fetch-json>
    </div>

    <div class="max-w-sm mx-auto">
      <fetch-json v-slot="{ json: contacts, loading }" url="/contacts.json">
        <div class="card">
          <h1 class="text-2xl font-bold mb-6">Your Contacts</h1>
          <div v-if="loading">Loading...</div>
          <contact-list v-else :contacts="contacts"></contact-list>
        </div>
      </fetch-json>
    </div>
  </div>
</template>

<script>
import ContactList from './ContactList.vue';
import FetchJson from './FetchJson.vue';

export default {
  components: {
    FetchJson,
    ContactList,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
