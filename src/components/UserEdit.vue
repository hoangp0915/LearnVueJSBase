<template>
  <div class="component">
  		<h3>You may edit the User here</h3>
  		<p>Edit me!</p>
  		<p>My Age: {{ userAge }}</p>
  		<button @click="editAge()">Change Age</button>
  </div>
</template>

<script>
	import {eventBus} from '../main.js'
export default {
	props:{
		userAge: Number,
	},
 	methods:{
 		editAge(){
 			this.userAge  = 22;
 			//this.$emit('ageWasEdit', this.userAge);//thông qua thằng cha
 			//eventBus.$emit('ageWasEdit', this.userAge);//sử dụng eventBus như xe bus vận chuyển giữ các con với nhau. Điểm đầu
 			eventBus.changeAge(this.userAge); //Sử dụng  methods changeAge bên main.js

 		}
 	}
}
</script>

<style scoped>
 	div{
 		background-color: lightgreen;
 	}
</style>
