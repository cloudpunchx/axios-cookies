<template>
    <div>
        <button @click="getCatImg">Get a cat picture!</button>
    </div>
</template>

<script>
import axios from 'axios';
import cookies from 'vue-cookies';

    export default {
        name: "CatButton",
        methods: {
            getCatImg() {
                axios.request({
                    url: "https://aws.random.cat/meow",
                    method: "GET"
                }).then((response)=>{
                    let src = response.data.file;
                    cookies.set(`Selection`, `cat`);
                    this.$root.$emit(`newDisplay`, src);
                }).catch((error)=>{
                    console.log(error);
                }).finally(()=>{
                    console.log("Final clause!");
                })
            }
        },
        mounted () {
            let selection = cookies.get(`selection`);
                if (selection == 'cat'){
                    this.getCatImg();
            }
        },
    }
</script>

<style scoped>

</style>