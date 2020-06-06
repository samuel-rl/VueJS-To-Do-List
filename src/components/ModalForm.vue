<template>
    <div class="modal">
        <div class="modal-content">
            <form>
                <div class="form-group">
                    <label class="labelAdd" for="action">Ajouter :</label>
                    <input v-model="formData.toDo" type="text" id="action" class="form-control">
                    <button v-on:click.prevent="addTodo" class="btn btn-primary mb-3">+</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
	name: 'ModalForm',
	data() {
		return {
			formData: {
				toDo: '',
			},
		};
	},
};
</script>

<style scoped>
.modal {
	display: block;
	position: fixed;
	width: 100%;
	height: 100%;
	overflow: auto;
	left: 0;
	top: 0;
	background-color: rgba(0, 0, 0, 0.2);
	z-index: 10;
}
.modal-content {
	position: absolute;
	left: 50%;
	top: 50%;
	-webkit-transform: translate(-50%, -50%);
	transform: translate(-50%, -50%);
    width: 80%;
}
</style>