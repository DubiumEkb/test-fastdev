<template>
	<div id="app">
		<div class="logo">
			<img alt="Logo" src="./assets/logo.png" />
		</div>
		<UsersList />
	</div>
</template>

<script>
import UsersList from './components/UsersList'
export default {
	components: {
		UsersList
	},
};
</script>

<style>
#app {
	display: flex;
	flex-direction: column;
}

#app .logo {
	margin: 0 auto;
}

#app .cards {
	display: flex;
	flex-direction: column;
}

#app .cards .card {
	display: flex;
	color: #221C44;
	background: #F0F6FF;
	cursor: pointer;
	margin-bottom: 15px;
}

#app .cards .card > div {
	padding: 10px 15px;
}

#app .cards .card.active {
	background: #221C44;
	color: #F0F6FF;
}
</style>