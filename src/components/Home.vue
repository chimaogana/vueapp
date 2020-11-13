<template>
	<div>
		<h1>HomePage</h1>
		<form @submit.prevent="add">
			<input type="text" v-model="newItem" />
			<button type="submit">Add</button>
		</form>

		<items :items="lists"></items>
	</div>
</template>
<script>
import items from "./Items";
export default {
	components: { items },
	data() {
		return {
			lists: [
				{ name: "Ogana chima" },
				{ name: "Andrew" },
				{ name: "Morgan" },
				{ name: "Vue" },
				{ name: "Angular" },
				{ name: "Laravel" }
			],
			newItem: null
		};
	},
	methods: {
		add() {
			this.lists.push({ name: this.newItem });
			this.newItem = null;
		}
	},
	created() {
		EventBu.$on("itemRemove", index => {
			this.lists.splice(index, 1);
		});
	}
};
</script>

<style></style>
