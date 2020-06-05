<template>
    <div class="container mt-5">

        <form>
            <div class="form-group">
                <label for="action">Ajouter :</label>
                <input v-model="formData.toDo" type="text" id="action" class="form-control">
            </div>
            <button v-on:click.prevent="addTodo" class="btn btn-primary mb-3">Add</button>

        </form>
        <ul>
            <li v-bind:key="index" v-for="(toDo, index) in arrayToDo">
                <item :toDo="toDo"></item>
            </li>
        </ul>
    </div>

</template>

<script>
import Item from './Item';

export default {
	name: 'Contenu',
	data() {
		return {
			formData: {
				toDo: '',
			},
			arrayToDo: ['Test', 'Test1', 'Test2'],
		};
    },
    methods :{
        addTodo: function(){
            this.arrayToDo.push(this.formData.toDo);
            this.formData.toDo = ''
        }
    },
	components: {
		Item: Item,
	},
};
</script>

<style scoped>
    h1 {
        margin-top: 100px !important;
    }

    ul {
        list-style: none;
        padding: 0;
    }
</style>

