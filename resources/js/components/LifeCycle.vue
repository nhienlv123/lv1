<template>
    <div id="my-text">
        This is my text: {{counter}}
    </div>
</template>

<script>
    export default {
        data() {
            return {
                counter: 0
            }
        },
        // beforeCreate() {
        //     console.log(this.message)
        // }
        // created() {
        //     console.log(this.message)
        //     console.log(document.getElementById('my-text').innerHTML)
        // }
        // beforeMount() {
        //     console.log(this.message)
        //     console.log(document.getElementById('my-text').innerHTML)
        // }
        // beforeUpdate() {
        //     console.log(this.counter)
        // },
        updated() {
            console.log(+this.$refs['dom-element'].textContent === this.counter)
        },
        created() {
            setInterval(() => {
                this.counter++
            }, 1000)
        }
    }
</script>

<style lang="scss" scoped>

</style>