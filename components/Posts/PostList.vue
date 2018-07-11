<template>
  <div class="posts-page">
		<section class="post-list">
			<PostPreview
				id="1"
				:is-admin="isAdmin"					 
				thumbnail="https://coastlinerehabcenters.com/wp-content/uploads/2018/06/office-space-400x284.jpg"
				title="Hello from post 1"
				previewText="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ducimus aperiam reiciendis ipsa beatae, in iste sed eum, molestiae, sit consequuntur dolores adipisci labore voluptatum veniam non. Odit, voluptatum, in, et possimus veniam nesciunt officiis suscipit nam iusto totam maiores."/>
			<PostPreview
				id="2"
		    :is-admin="isAdmin"
				thumbnail="https://coastlinerehabcenters.com/wp-content/uploads/2018/06/black-couches-400x284.jpg"
				title="Hello from post 2"
				previewText="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ducimus aperiam reiciendis ipsa beatae, in iste sed eum, molestiae, sit consequuntur dolores adipisci labore voluptatum veniam non. Odit, voluptatum, in, et possimus veniam nesciunt officiis suscipit nam iusto totam maiores."/>
			<PostPreview
				id="3"
				:is-admin="isAdmin"
				thumbnail="https://coastlinerehabcenters.com/wp-content/uploads/2018/06/coastline-office-entrance-400x284.jpg"
				title="Hello from post 3"
				previewText="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi ducimus aperiam reiciendis ipsa beatae, in iste sed eum, molestiae, sit consequuntur dolores adipisci labore voluptatum veniam non. Odit, voluptatum, in, et possimus veniam nesciunt officiis suscipit nam iusto totam maiores."/>
		</section>
  </div>
</template>

<script>
	import PostPreview from '@/components/Posts/PostPreview'

	export default {
		components: {
			PostPreview
		},
		props: {
			isAdmin: {
				type: Boolean,
				default: false
			}
		}
	}
</script>

<style scoped>
	.post-list {
		display: flex;
		padding: 20px;
		box-sizing: border-box;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
	}
</style>