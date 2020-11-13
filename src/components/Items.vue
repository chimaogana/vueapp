<template>
	<ul>
		<li
			v-for="(item, index) in items"
			:key="item.name"
			v-if="item.name !== 'React'"
		>
			{{ item.name }}
			<button @click="remove(index)">X</button>
		</li>
		<li v-else>No React Allow here</li>
	</ul>
</template>

<script>
export default {
	props: ["items"],
	methods: {
		remove(index) {
			return EventBu.$emit("itemRemove", index);
		}
	}
};
</script>

<style></style>
