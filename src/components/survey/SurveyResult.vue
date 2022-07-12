<template>
  <li>
    <p>
      <span class="highlight">{{ name }}</span> rated the learning experience
      <span :class="ratingClass">{{ rating }}</span>.
      <small-delete @click="deleteSingle">Delete2</small-delete>
    </p>
  </li>
</template>

<script>

export default {
  props: ['name', 'rating'],
  computed: {
    ratingClass() {
      return 'highlight rating--' + this.rating;
    },
  methods: {
    deleteSingle() {
      const d_json = process.env.VUE_APP_JSON;
      fetch(d_json, {method: 'DELETE'});
    }
  }
  },
};
</script>

<style scoped>
li {
  margin: 1rem 0;
  border: 1px solid #ccc;
  padding: 1rem;
}

h3,
p {
  font-size: 1rem;
  margin: 0.5rem 0;
}

.highlight {
  font-weight: bold;
}

.rating--poor {
  color: #b80056;
}

.rating--average {
  color: #330075;
}

.rating--great {
  color: #008327;
}

</style>