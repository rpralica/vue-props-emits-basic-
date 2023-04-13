<template>
  <li>
    <h2>{{ firstName }} {{ hasFavorites }}</h2>
  </li>
  <ul v-if="detailsAreVisible">
    <li>
      <strong>Phone: {{ phoneNumber }}</strong>
    </li>
    <li>
      <strong>Email:{{ emailAddress }}</strong>
    </li>
  </ul>
  <button @click="toggleVisible()">{{ captionVisibility }} Details</button>
  <button @click="toggleFavorite()">Togle Favorite</button>
</template>

<script>
export default {
  emits: ['toggle-favorite'],
  props: ['id', 'firstName', 'phoneNumber', 'emailAddress', 'isFavorite'],
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleVisible() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.id);
    },
  },
  computed: {
    captionVisibility() {
      return this.detailsAreVisible ? ' Hide' : 'Show';
    },
    hasFavorites() {
      return this.isFavorite ? '( Fav )' : '';
    },
  },
};
</script>

<style>
li {
  list-style: none;
}
button {
  background: deepskyblue;
  border-color: white;
  color: white;
}
</style>
