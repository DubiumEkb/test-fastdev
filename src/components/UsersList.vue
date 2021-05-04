<template>
	<div>
		<div class="cards">
			<div
				v-bind:class="'card' + [item.status ? ' active' : '']"
				v-for="item in items"
				v-bind:key="item.id"
				v-bind:id="'card_' + item.id"
				@click="item.status = !item.status"
				>
				<div>{{ item.id }}</div>
				<div>{{ item.displayName }}</div>
				<div>{{ item.birthdate }}</div>
				<div>{{ item.email }}</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			items: null
		}
	},
	created() {
		fetch("https://fastdevmockend.gennadiyfayrush.repl.co/users", {
			"Content-Type": "application/json",
			method: 'GET'
		})
		.then(response => response.json())
		.then(data => {
			let addProps = (itemStatus) => {
				itemStatus.status = false;
				return itemStatus;
			},
			itemList = data.map(itemStatus => addProps(itemStatus))

			this.items = itemList
		})
		.catch(error => console.error(error));
	}
}
</script>