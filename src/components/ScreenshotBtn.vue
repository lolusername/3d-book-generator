<template>
	<div>
		  <a v-on:click="toggleMode" href="#" class="float">
        <i class="fas fa-2x fa-images"></i>
			<div>Screenshot Mode</div>
			
    </a>
		<article class="float under">
				<button @click="toggleBorder" class="btn btn-link">Toggle Border</button>
			</article>
	</div>
  
</template>

<script>

import BookForm from "./BookForm.vue";

export default {
  name: "ScreenshotBtn",
  methods: {
	  toggleMode() {
		  $("form").toggle();
		  $(".book-wrapper").toggleClass("full-height")
		},
		toggleBorder() {
			$("#tridiv").toggleClass("borders")
		}
  }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" >
.float{
	&.under{
		bottom:2px;
		background-color: transparent;
		padding:auto;
		box-shadow: none;
	}
	position:fixed;

	bottom:40px;
	right:40px;
	background-color:#263238;
	color:#FFF;
	border-radius:50px;
	text-align:center;
	box-shadow: 2px 2px 3px #999;
	padding: 4px 24px;
}
a {
	text-decoration: none !important;
}
.my-float{
	margin-top:22px;
}
.full-height{
	height:100vh;
	}

</style>
