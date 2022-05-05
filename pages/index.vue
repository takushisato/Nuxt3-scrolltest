<template>
  <div class="container">
    <div class="nav">
      <a href="#fast" @click="returnFast()"><p>１へ飛ぶ</p></a>
      <a href="#second" @click="returnSecond()"><p>２へ飛ぶ</p></a>
      <a href="#third" @click="returnThird()"><p>３へ飛ぶ</p></a>
      <a href="#ford" @click="returnFord()"><p>４へ飛ぶ</p></a>
      <a href="#five" @click="returnFive()"><p>５へ飛ぶ</p></a>
    </div>
    <div class="test" ref="fast">Hello world1</div>
    <div class="test" ref="second">Hello world2</div>
    <div class="test" ref="third">Hello world3</div>
    <div class="test" ref="ford">Hello world4</div>
    <div class="test" ref="five">Hello world5</div>
    <button @click="returnTop">TOPに戻る</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      fastDiv: '',
      secondDiv: '',
      thirdDiv: '',
      fordDiv: '',
      fiveDiv: '',
    }
  },
  mounted(){
    this.fastDiv = this.$refs.fast.getBoundingClientRect();
    this.secondDiv = this.$refs.second.getBoundingClientRect()
    this.thirdDiv = this.$refs.third.getBoundingClientRect()
    this.fordDiv = this.$refs.ford.getBoundingClientRect()
    this.fiveDiv = this.$refs.five.getBoundingClientRect()
  },
  methods: {
    returnFast() {
      window.scrollTo({
        top: this.fastDiv.y,
        behavior: 'smooth'
      })
    },
    returnSecond() {
      window.scrollTo({
        top: this.secondDiv.y,
        behavior: 'smooth'
      })
    },
    returnThird() {
      window.scrollTo({
        top: this.thirdDiv.y,
        behavior: 'smooth'
      })
    },
    returnFord() {
      window.scrollTo({
        top: this.fordDiv.y,
        behavior: 'smooth'
      })
    },
    returnFive() {
      window.scrollTo({
        top: this.fiveDiv.y,
        behavior: 'smooth'
      })
    },
    returnTop() {
      window.scrollTo({
        top: 0,
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
.nav{
  display: block;
}
.test {
  margin: 30px;
  height: 50vh;
  background: pink;
  font-size: 40px;
}
</style>