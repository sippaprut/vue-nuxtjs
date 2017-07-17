<template>
	 <section class="container">
		{{ title }}
		<div class="obit-items" v-for="obit in obits">
			{{ obit.email }}
		</div>

	 </section>
</template>

<script>
import axios from 'axios'
export default {
  head: {
    title: 'Obit Page',
    meta: [
      { name: 'description', content: 'Obit page description' },
      { name: 'og:img', content: 'https://faceboox.com' }
    ]
  },
  asyncData ({ params }) {
    return axios.get('https://randomuser.me/api/')
    .then(({data}) => {
      return { obits: data.results, title: 'Hello Async' }
    })
  },
  data () {
    return { title: 'Hello Nuxtjs' }
  }
}
</script>

