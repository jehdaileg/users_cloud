<template>

	<div class="users">

		<h4>Utilisateurs Actifs</h4>

		<div class="users_box">

		<img :src="picture" :alt="name" :class="gender">	
			
		<h4>{{ name }}</h4>
		<h4>{{ surname }}</h4>
		<h4>{{ email }}</h4>
		<h4>{{ entreprise }}</h4>

		<button :class="gender" @click="getUser">Get Random User</button>

		</div>
		
	</div>
	

</template>

<script>

export default {

	name : "users",

	data() {

		return {

			name : "Jonathan",

			surname : "Derrick",

			email : "jonhathanderrick@gmail.com",

			entreprise : "facebook community", 

			picture : "https://randomuser.me/api/portraits/men/1.jpg",

			gender : "male"


		}
	},

	methods : {

		getUser(){

			
			//console.log(results)

			this.name = "Vanessa",

			this.surname = "Craig",

			this.email = "vanessacraig@gmail.com",

			this.entreprise = "twitter community",

			this.picture = "https://randomuser.me/api/portraits/women/5.jpg",

			this.gender = "female"

		}


	}


}
	

</script>


<style scoped>
	
	.users_box {

		display : flex; 

		justify-content : center;

		align-items : center;

		margin : auto;

		padding : auto ;

		text-align :center;

		flex-direction : column;

	}

	img {

		border-radius : 50%;

		border : 5px #333 solid;

		margin-bottom : 0.5rem;


	}

	.male {

		border-color : steelblue;

		border-background : steelblue;


	}

	.female {

		border-color : pink ;

		border-background : pink;

		color : pink;

	}

</style>