<template>
  <div class="image-grid">
        <img v-for="(image, index) in images" :key="index" :src="image"/> 
        <!-- Hay q añadir :key="algo único como id, image, url,..."" pq es la sintaxis de este elemento. Si ponemos v-for="(url, index)" Vue sabe q el primer argumento se refiere a cada elemento del array y el segundo, se refiere a su posición o index en dicha array -->
        </div>
</template>

<script>
export default {
    name: "ImageGrid",
    components: {},
    data(){
        return {

        }
    },
    methods: {

    },
    props: ["images"]

}
</script>

<style>

</style>
