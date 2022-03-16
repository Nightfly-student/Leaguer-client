<template>
  <div class="container-xl">
    <h2 class="pt-4">Settings</h2>
    <nav class="navbar navbar-expand-lg navbar-light">
      <div class="navbar-nav">
        <ul class="nav nav-tabs">
          <li class="nav-item">
            <a
              class="nav-link pointer"
              :class="{ active: profile }"
              @click="changeTab('profile')"
              aria-current="page"
              >profile</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link pointer"
              :class="{ active: additional }"
              @click="changeTab('additional')"
              >advanced settings</a
            >
          </li>
        </ul>
      </div>
    </nav>
    <ProfileSettings v-if="profile" />
    <AdvancedSettings v-if="additional" />
  </div>
</template>

<script>
import ProfileSettings from "../components/settings/ProfileSettings.vue";
import AdvancedSettings from "../components/settings/AdvancedSettings.vue";

export default {
  name: "SettingsView",
  components: {
    ProfileSettings,
    AdvancedSettings,
  },
  data() {
    return {
      profile: true,
      additional: false,
    };
  },
  methods: {
    changeTab(value) {
      this.profile = false;
      this.additional = false;
      this[value] = true;
    },
  },
};
</script>

<style></style>
