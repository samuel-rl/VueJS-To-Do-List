<template>
    <div class="container mt-5">
        <modal-form></modal-form>
        <ul>
            <li v-bind:key="index" v-for="(toDo, index) in arrayToDo">
                <item v-bind:id="index" :toDo="toDo" :suppression="suppression"></item>
            </li>
        </ul>
    </div>

</template>

<template>
    <button v-on:click="changeIsAddModal" type="button" class="btn btn-primary addButton">+</button>
</template>


<script>
export default {
    name: 'ButtonAdd',
    methods: {
        changeIsAddModal: function(){
            this.$emit('changeIsAddModal', true)
        }
    }
};
</script>

<style scoped>
.addButton{
    width: 80px;
    height: 80px;
    position: absolute;
    bottom: 40px;
    right: 20px;
    font-size: 30px;
    transition: all ease 0.6s;
}

.addButton:hover{
    border-radius: 10px;
}
</style>

