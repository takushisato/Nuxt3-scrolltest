<template>
  <div class="container">
    <div class="test" id="fast">Hello world1</div>
    <div class="test" id="second">Hello world2</div>
    <div class="test" ref="third">Hello world3</div>
    <div class="test" id="ford">Hello world4</div>
    <div class="test" id="five">Hello world5</div>
    <button @click="returnTop">TOPに戻る</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      rect: '',
    }
  },
  mounted(){
    this.rect = this.$refs.third.getBoundingClientRect()
    console.log(this.rect);
  },
  methods: {
    returnTop() {
      window.scrollTo({
        top: this.rect.y,
        behavior: 'smooth'
      })
    }
  }
}
</script>
<style scoped>
.container {
  text-align: center;
}
.test {
  margin: 30px;
  height: 50vh;
  background: pink;
  font-size: 40px;
}

</style>