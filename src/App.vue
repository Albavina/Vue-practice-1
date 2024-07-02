<!-- TEMPLATE 
    - This is the content we will see. 
    - We write it in HTML-->
<template>
    <div class="App">
        <h1>Hey FSPT30! 👋</h1>

        <button type="submit" class="toggle-button" @click="toggleForm">{{ showForm ? "Hide form" : "Add images!" }}</button> 
        <!-- This is for the BUTTON to say something different depending on a condition -->
        
        <Form :showForm ="showForm"/> 
        <!-- We create here the variable with :variableName that will connect with the component Form through a Prop -->
        
        <ImageGrid :image="images"/>
    </div> 

</template>
    
<!-- SCRIPTS 
    - These will add data and functionality to our app.
    - We write them in Javascript. -->
<script>
    import ImageGrid from "./components/ImageGrid.vue";
    import Form from "./components/Form.vue";

    export default {
        //  The name of our component. It should match the file name.
        name: 'App',
        // This is where we list any components we will import.
        components: {
            ImageGrid,
            Form
        },
        // This is where we create variables (in the return statement)
        data() {
            return {
                images : [],
                // input: "", We do not need this here because it is on the Form.vue file.
                showForm: false,
            }
        },
        // This is where we define our functions.
        methods: {
            addImage () {
                this.images.push(this.input);
                this.input="";//We do this to clear the input after we submit the image.
            },
            toggleForm(){
                this.showForm = !this.showForm;
            }
        }
    }
</script>
    
<!-- STYLES
    - These will add style and formatting to our content.
    - We write it in CSS -->
<style>
    .App {
        margin: 0 auto;
        font-family: Arial, Helvetica, sans-serif;
        text-align: center;
    }

    .image-grid{
        text-align: center;
        margin: 2em auto;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 2em
        
    }

    button{
        display: block;
        margin: auto;
        margin-top: 1em;
    }

    img{
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
        border-radius: 10px;
    }

   
</style>