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
    <button type="button" class="btn btn-primary addButton">+</button>
</template>


<script>
export default {
	name: 'ButtonAdd',
};
</script>

<style scoped>
.addButton{
    width: 60px;
    height: 60px;
    position: absolute;
    bottom: 10px;
    right: 10px;
    font-size: 30px;
    transition: all ease 0.6s;
}

.addButton:hover{
    border-radius: 20px;
}
</style>

