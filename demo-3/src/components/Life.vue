<template>
  <div>
    <p>学习生命周期</p>
    <p>{{ msg }}</p>
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      msg: 'Hello, vue.'
    }
  },
  beforeCreate() {
    console.log('before create')
    console.log(this.msg)
  },
  created() {
    console.log('created')
    console.log(this.msg)
  }
}
</script>

<style>

</style>