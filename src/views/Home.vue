<template>
  <div class="home">
    <!-- <div v-if="error" class="error">Could not fetch the data</div>
    <div v-if="documents">
      <div v-for="doc in documents" :key="doc.id">{{ doc.title }}</div>
    </div> -->
    <div v-if="error" class="error">Could not fetch the data</div>
    <div v-if="documents">
      <ListView :playlists="documents" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ListView from '@/components/ListView';
import getCollection from '@/composables/getCollection';

export default {
  name: 'Home',
  components: { ListView },
  setup() {
    const { error, documents } = getCollection('playlists');

    return { error, documents };
  },
};
</script>
