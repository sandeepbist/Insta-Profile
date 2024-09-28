<script>
	import Profile from './Profile.svelte';
	import Posts from './Posts.svelte';
	let username = "";
	let INSTA = "https://instagram.com/";
	let user = null;
	let posts = null;
	async function searchUser(){
		let res = await fetch(INSTA+username+"?__a=1",{
			method:"GET"
		});
		let data = await res.json();
		console.log(data);
		user = data.graphql.user;
		posts = user.edge_owner_to_timeline_media.edges;
	}
</script>

<style>
	.header {
		padding:10px 0px;
		text-align:center;
		background:#111;
	}
</style>

<div class="header">
	<input type="text" bind:value={username}/>
	<button on:click={searchUser}>
		Search
	</button>
</div>
{#if user}
	<Profile {user}/>
	<Posts {posts} />
{/if}