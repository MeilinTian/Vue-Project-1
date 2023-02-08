<template>

    <div>
        <input ref="myInp" type="text" placeholder="this is an input." v-if="isShow">
        <button v-else @click="btn">SEARCH</button>
    </div>
 
</template>

<script>
export default {
    data() {
        return {
            isShow: false
        }
    },
    methods: {
        async btn() {
            this.isShow = true;
            await this.$nextTick()
            this.$refs.myInp.focus()
        }
    }
}
</script>

<style>

</style>