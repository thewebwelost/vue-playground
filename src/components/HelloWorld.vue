<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<script>
export default {
  data() {
    return {
      count: 0,
      isDisabled: this.count > 0
    }
  },

  methods: {
    increment() {
      this.count++
      console.log('this.count', {count:this.count, dis:this.isDisabled})
    }
  },

  mounted() {
    console.log(`The initial count is ${this.count}.`)
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green" v-if="isDisabled">{{ msg }}</h1>
    <button @click="increment" :disabled="isDisabled">count: {{count}}</button>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
