<template>
  <div class="component">
  		<h1>The User Component</h1>
  		<p>I'm an awesome Developer! I'm {{name}} and {{ age }} years old</p>
  		<button @click="changeName">Change Name</button>
  		<hr>
  		<div class="row">
  			<div class="col-xs-12 col-sm-6">
  				<app-user-detail 
  					v-bind:ctName="name" 
  					@nameWasReset="name = $event"  
					:resetNameCallBack="resetName"
					:userAge="age"
  					></app-user-detail>
  			</div>
  			<div class="col-xs-12 col-sm-6">
  				<app-user-edit :userAge="age" @ageWasEdit="age = $event" ></app-user-edit> <!-- thằng con userEdit gửi tới event ageWasEdit thay đổi age = $event -->
  			</div>
  		</div>
  </div>
</template>

<script>
	import UserEdit from './UserEdit.vue';
	import UserDetail from './UserDetail.vue';
export default {
	data: function(){
		return {
			name: 'Genos',
			age: 18
		}
	},
	methods: {
		changeName(){
			this.name = 'Hoang';
		},
		resetName(){
			this.name = 'Genos';
		}
	},
 	components: {
 		appUserDetail: UserDetail,
 		appUserEdit: UserEdit,
 	}	
}
</script>

<style scoped>
 	div{
 		background-color: lightblue;
 	}
</style>
