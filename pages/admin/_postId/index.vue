<template>
  <div class="admin-post-page">
		<section class="update-form">
	  	<AdminPostForm :post="loadedPost" />
	</section>
	</div>
</template>

<script>
	import AdminPostForm from '@/components/Admin/AdminPostForm'
  
	export default {
		layout: 'admin',
		components: {
			AdminPostForm
		},
		data() {
			return {
				loadedPost: {
					author: 'Nathan Arnold',
					title: 'Nate strikes again',
					content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Modi fugiat iste molestiae ipsum illo, inventore, quod quo minus ducimus distinctio. Magni, hic. Iusto rem sunt vel, harum tempora laboriosam aspernatur odio, consequatur provident repellendus id vitae placeat doloremque error non quam, debitis aperiam temporibus recusandae officiis in, sapiente porro fuga! Velit excepturi laudantium quae culpa eum totam pariatur impedit numquam alias optio aspernatur labore illo maiores vero voluptatum blanditiis, corporis, fugiat voluptas nisi. Id eaque esse repellendus illum dolorum saepe optio fugit molestias corporis repellat ipsum eligendi cumque cupiditate non, cum qui maiores odio quos. Suscipit libero debitis, laboriosam blanditiis!',
					thumbnailLink: '~assets/images/N8.jpg'
				}
			}
		}
	}
</script>

<style scoped>
	.update-form {
		width: 90%;
		margin: 20px auto;
	}
	@media (min-width: 768px) {
		.update-form {
			width: 500px;
		}
	}
</style>