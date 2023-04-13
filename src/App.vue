<template>
  <the-header>
    <h1>Moja Porodica</h1>
  </the-header>
  <family-contact
    v-for="fam in family"
    :key="fam.id"
    :id="fam.id"
    :first-name="fam.name"
    :phone-number="fam.phone"
    :email-address="fam.email"
    :is-favorite="fam.isFavorite"
    @toggle-favorite="togFav"
  ></family-contact>
</template>

<script>
import FamilyContact from './components/FamilyContact.vue';
import TheHeader from './components/TheHeader.vue';
export default {
  data() {
    return {
      family: [
        {
          id: 'matej',
          name: 'Matej Pralica',
          phone: '111-1111-11111',
          email: 'matej@gmail.com',
          isFavorite: true,
        },
        {
          id: 'rade',
          name: 'Rade Pralica',
          phone: '222-2222-2222',
          email: 'rade@gmail.com',
          isFavorite: false,
        },
        {
          id: 'magi',
          name: 'Magdalena Prišić',
          phone: '333-3333-33333',
          email: 'magi@gmail.com',
          isFavorite: true,
        },
      ],
    };
  },
  methods: {
    togFav(familyId) {
      const identFamily = this.family.find(fam => fam.id === familyId);
      identFamily.isFavorite = !identFamily.isFavorite;
    },
  },

  components: {
    FamilyContact,
    TheHeader,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
