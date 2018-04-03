<template>
  <div class="home clearfix">
  	<Carousel />
  	<Img />
  	<News />
  	<Newloupan />
  	<Contace />
  	<Form />
  	<Newloupan />
  	<Address />
  	<Newloupan />
  </div>
</template>

<script>
// @ is an alias to /src
import Carousel from '@/components/Carousel.vue'
import Img from '@/components/Img.vue'
import News from '@/components/News.vue'
import Newloupan from '@/components/Newloupan.vue'
import Contace from '@/components/Contace.vue'
import Form from '@/components/Form.vue'
import Address from '@/components/Address.vue'

export default {
  name: 'home',
  components: {
    Carousel,
    Img,
    News,
    Newloupan,
    Contace,
    Form,
    Address
  }
}
</script>     
<style>
	.home{
		margin-bottom: 60px;
	}
</style>
