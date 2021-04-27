<template>
  <div>
    <h1>SearchBar component</h1>
    <input type="text" @input="setInput" />
  </div>
</template>

<script>
export default {

  data(){
    return {

    }
  },

  methods: {

    setInput(e){
      this.$emit("termChange", e.target.value)
    }

  }

}
</script>

<style>

</style>