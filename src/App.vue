<template>
  <div class="min-h-screen bg-grey-darker p-8">
    <div class="max-w-sm mx-auto">
      <!-- <user-settings-form></user-settings-form> -->
      <!-- <app-date-picker></app-date-picker> -->
      <!-- <app-modal></app-modal> -->
      <!-- <portal-app></portal-app> -->
      <!-- <content-app></content-app> -->
      <!-- <extending-component></extending-component> -->
      <!-- <scoped-slot></scoped-slot> -->
      <!-- <render-functions></render-functions> -->
      <!-- <provider-component></provider-component> -->
      <!-- <renderless-component></renderless-component> -->
      <!-- <element-query></element-query> -->
      <!-- <compound-components></compound-components> -->
      <!-- <sortable-list></sortable-list> -->
      <search-select></search-select>
    </div>
  </div>
</template>

<script>
// import UserSettingsForm from "./components/01-controlled/UserSettingsForm.vue"
// import AppDatePicker from "./components/03-wrapping-external-libraries/AppDatePicker.vue"
// import AppModal from './components/04-encapsulating-behavior/AppModal.vue';
// import PortalApp from './components/06-portals/PortalApp.vue';
// import ContentApp from './components/08-injecting-content/ContentApp.vue';
// import ExtendingComponent from './components/10-extending-components/MainApp.vue';
// import ScopedSlot from './components/11-scoped-slots/MainApp.vue';
// import RenderFunctions from './components/12-render-functions/MainApp.vue';
// import ProviderComponent from './components/16-provider-components/MainApp.vue';
// import RenderlessComponent from './components/17-renderless-components/MainApp.vue';
// import ElementQuery from './components/25-element-query/MainApp.vue';
// import CompoundComponents from './components/26-compound-components/MainApp.vue';
// import SortableList from './components/27-sortable-list/MainApp.vue';
import SearchSelect from './components/28-search-select/MainApp.vue';

export default {
  components: {
    // UserSettingsForm,
    // AppDatePicker,
    // AppModal,
    // PortalApp,
    // ContentApp,
    // ExtendingComponent,
    // ScopedSlot,
    // RenderFunctions,
    // ProviderComponent,
    // RenderlessComponent,
    // ElementQuery
    // CompoundComponents
    // SortableList
    SearchSelect
  }
}
</script>

<style src="./assets/css/app.css"/>