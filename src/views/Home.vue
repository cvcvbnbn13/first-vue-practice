<template>
  <div class="home">
  	<article v-for="art in articles">
  		<h3>{{art.title}}</h3>
  		<i> {{art.date}} </i>
  		<span> {{art.content|subContent}} </span>
  	</article>
  </div>
</template>


<script>
import axios from 'axios'

export default {
  name: 'Home',
     mounted () {
      const api = "https://us-central1-expressapi-8c039.cloudfunctions.net/app/article"
      axios.get(api)
        .then(result=>{
          this.articles = result.data.data
        })
    },
    data () {
      return {
        articles : null,
      }
    },
    filters:{
    	subContent:(content)=>{
    		return content.substring(0,150)
    	}
    }
}

</script>

<style scoped="">
	article{
		display: flex;
		padding-left: 2rem;
		margin: 2rem auto;
		flex-direction: column;
		align-items: flex-start;
		justify-content: center;
		width: 80vw;
		height: 300px;
		background-color: #dddddd;
	}
</style>

