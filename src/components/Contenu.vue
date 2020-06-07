<template>
    <div class="container mt-5">
        <modal-form></modal-form>
        <button-add></button-add>
        <ul>
            <li v-bind:key="index" v-for="(toDo, index) in arrayToDo">
                <item v-bind:id="index" :toDo="toDo" :suppression="suppression"></item>
            </li>
        </ul>
    </div>

</template>

<script>
import Item from './Item';
import ModalForm from './ModalForm';
import ButtonAdd from './ButtonAdd';

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
	methods: {
		addTodo: function() {
			if (this.formData.toDo != '') {
				this.arrayToDo.push(this.formData.toDo);
				this.formData.toDo = '';
			}
		},
		suppression: function(e) {
			this.arrayToDo.splice(e.target.parentNode.id, 1);
		},
	},
	components: {
        Item: Item,
        ModalForm: ModalForm,
        ButtonAdd: ButtonAdd
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

.divForm {
	text-align: center;
}

.displ {
	width: 80%;
}

.block {
	display: inline-block !important;
}

.labelAdd {
	margin-right: 10px;
}

.btn-add {
	cursor: pointer;
	margin-left: 10px;
}
</style>

