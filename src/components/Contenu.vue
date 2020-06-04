<template>
    <div class="container mt-5">

        <h1> Taches à accomplir </h1>

        <form>
            <div class="form-group">
                <label for="action">Ajouter :</label>
                <input type="text" id="action" class="form-control">
            </div>
            <button class="btn btn-primary">Add</button>

        </form>
        <ul>
            <li v-bind:key="index" v-for="(toDo, index) in array">
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
			array: ['Test', 'Test1', 'Test2'],
		};
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
    }
</style>

