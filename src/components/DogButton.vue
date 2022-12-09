<!-- MAKE AXIOS REQUEST SNIPPET -->

<template>
    <div>
        <button @click="getDogImg">Get a dog picture!</button>
    </div>
</template>

<script>
import axios from 'axios';
import cookies from 'vue-cookies';

    export default {
        name: "DogButton",
        methods: {
            getDogImg() {
                // RESEARCH AXIOS.GET OR AXIOS.___REQUEST
                axios.request({
                    url: "https://dog.ceo/api/breeds/image/random",
                    method: "GET"
                }).then((response)=>{
                    let src = response.data.message;
                    this.$root.$emit(`newDisplay`, src);
                    cookies.set(`Selection`, `dog`);
                }).catch((error)=>{
                    console.log(error);
                    // 'finally clause' that says regardless of what happened above, execute this code after:
                    // useful to clean something up, back end uses it more
                    // eg. user puts in search, but you want to clear the search bar regardless
                    // kind of rare to use in front end but you might
                }).finally(()=>{
                    console.log("Final clause!");
                })
            },
        },
        mounted () {
            let selection = cookies.get(`selection`);
                if (selection == 'dog'){
                    this.getDogImg();
            }
        },
    }
</script>

<style scoped>

</style>