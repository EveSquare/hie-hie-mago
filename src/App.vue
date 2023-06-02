<script>
import HelloWorld from './components/HelloWorld.vue'
import MainSelector from "./components/MainSelector.vue";

export default {
  name: 'App',
  components: {
    HelloWorld,
    MainSelector
  },
  data() {
    return {
      selectors: [{
        value: '',
      }, {
        value: '',
      }],
    }
  },
  methods: {
    change(index, value) {
      this.selectors[index].value = value;
    },
    removeSelector(index) {
      console.log('removeSelector', index);
      // 最後の一個は消せない
      if (this.selectors.length === 1) {
        return;
      }
      this.selectors.splice(index, 1);
    },
    addSelector() {
      this.selectors.push({
        value: '',
      });
    }
  },
  computed: {
    result() {
      return this.selectors.map(selector => selector.value).join('の');
    }
  }
}
</script>

<template>
  <div v-for="(selector, index) in selectors">
    <MainSelector
      :key="index"
      :index="index"
      @change="change"
      @removeSelector="removeSelector"
    />
  </div>
  <div>
    <button @click="addSelector">+</button>
  </div>
  <textarea cols="30" rows="10" :value="result"></textarea>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
