<template>
	<q-toolbar clss='row'>
		<div class='col-10'>
			<a class="flex">Page1</a>
			<a class="flex">Page2</a>
			<a class="flex">Page3</a>
		</div>
		<q-btn class='col-2' label='Connexion' round @click='connexionB=true' />
		<q-modal v-model="connexionB">
			<h3>Connectez-Vous</h3>
			<p class="flex flex-center">Ne rien faire sur cette modale</p>
		</q-modal>
	</q-toolbar>
</template>

<style>
</style>

<script>

export default {
	name:'barreMenu',
	data () {
		return {
			connexionB:false,
		}
	  }
	}
</script>