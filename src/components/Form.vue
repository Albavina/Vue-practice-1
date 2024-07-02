<template>
<div class="Form">
    <form v-if="showForm">
        <label for="image">Add image: </label>
        <input name="image" v-model="input"/>
        <!-- When we copy and paste from the parent, we have to be carfull that we copy also the Data we need to make it work. In this case, only input is needed. -->
        <button type="submit" @click.prevent="addImage">Submit</button>
        <!-- Add .prevent here to avoid that submit automatically refresh the page when executed-->
    </form>
</div>
</template>

<script>
    export default {
        //  The name of our component. It should match the file name.
        name: 'Form',
        // This is where we list any components we will import.
        components: {
            ImageGrid},
        // This is where we create variables (in the return statement)
        props: ["showForm"],
        data() {
            return {
                input: "",
                // We only leave input because this is the only one we need for the form
            }
        },
        // This is where we define our functions.
        methods: {
            // addImage () {
            //     this.images.push(this.input);
            //     this.input="";//We do this to clear the input after we submit the image.
            // },
            // toggleForm(){
            //     this.showForm = !this.showForm;
            // }
        }

}
</script>

<style>

</style>