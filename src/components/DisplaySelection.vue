<template>
    <div>
        <img :src="imageSrc">
    </div>
</template>

<script>
    export default {
        name: "DisplaySelection",
        data() {
            return {
                imageSrc: ""
            }
        },
        methods: {
            showPicture(src) {
                this.imageSrc = src;
            }
        },
        mounted () {
            this.$root.$on(`newDisplay`, this.showPicture);
        },
    }
</script>

<style scoped>
img{
    width: 40vw;
}
</style>