<template>
  <div class="min-h-screen bg-grey-darker p-8">
    <div class="max-w-sm mx-auto">
      <contact-list :pseudo-slot="props => props.contact.name.first">
        <!-- <a slot-scope="{ contact }" :href="`/contacts/${contact.id}`">
          {{ contact.name.first }}
        </a> -->
        <a slot-scope="{contact}" :href="`/contacts/${contact.id}`"></a>
      </contact-list>
    </div>
  </div>
</template>

<script>
import ContactList from './ContactList.vue'

export default {
  components: {
    ContactList,
  },
  data() {
    return {}
  }
}
</script>

