<template>
  <div class="component">
  		<h3>Information User Details</h3>
  		<p>List Details</p>
  		<p>My name: {{ reverseName() }}</p>
  		<p>My age: {{ userAge }}</p>
  		<button @click="resetName()">Reset Name</button>
  		<button @click="resetNameCallBack()">ResetName Callback</button>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
	//props chuyền dữ liệu từ cha sang con và các COM con truyền thông báo đến các COM cha thông qua các sự kiện
 	props: {
 		ctName: {
 			type: Object,
 			default: 'Genos'
 		},
 		resetNameCallBack: Function,
 		userAge: Number
 	},
 	methods:{
 		reverseName(){
 			return this.ctName.split('').reverse().join('');
 		},
 		resetName(){
 			this.ctName = 'Genos';
 			this.$emit('nameWasReset', this.ctName); //gửi sự kiện lên thằng bố và thằng bố tiếp nhận
 		}
 	},
 	created(){
 		eventBus.$on('ageWasEdit', (age)=>{ //Điểm đuôi, tiếp nhân ageWasEdit từ UserEit
 			this.userAge = age
 		}) 	}
}
</script>

<style scoped>
 	div{
 		background-color: lightcoral;
 	}
</style>
