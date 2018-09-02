<template>
	<barreMenu />
	<q-carousel >
	  <q-carousel-slide v-for='i of manege' :img-src="i" />
	</q-carousel>
	<section>
		<q-input v-model="inputEnvoyer" placeholder="Entrez un mot" />
		<small v-if='txtRouge' id='txtEnRouge' > Vous devez obligatoirement rentrez une donnée </small>
		<q-btn label="envoyer" @click='atEnvoyerClic' />
		<p v-if='resB' > RESULTAT : {{res}}</p>
		
	</section>
</template>

<style>
#txtEnRouge{color:red;}
</style>

<script>
import barreMenu from 'components/barreMenu'

export default {
  components:[barreMenu],
  data () {
    return {
		manege:[
		"statics/cas.png",
		"statics/roux.png",
		"statics/sel.png",
		],
		inputEnvoyer:'',
		txtRouge:false,
		res:'',
		resB:false,
    }
  },
  methods:{
	atEnvoyerClic:function(){
		if(this.inputEnvoyer.length==0)this.txtRouge=false;
		else{
			this.res = [...this.inputEnvoyer].reverse().join('');	//string->array->reverse->string
			this.txtRouge = false;
			this.resB = false;
		}
	}
  },
}
</script>