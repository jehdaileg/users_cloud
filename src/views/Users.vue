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

		 async	getUser(){

		 	const res = await fetch("https://randomuser.me/api")

		 	const { results } = await res.json()


	
			//console.log(results)

			this.name = results[0].name.first,

			this.surname = results[0].name.last,

			this.email = results[0].email,

			this.entreprise = results[0].location.state,

			this.picture = results[0].picture.large,

			this.gender = results[0].gender

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