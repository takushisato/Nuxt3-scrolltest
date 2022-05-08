<template>
  <div class="container">
    <div class="nav">
      <a href="#fast" @click="returnScroll(1)"><p>１へ飛ぶ</p></a>
      <a href="#second" @click="returnScroll(2)"><p>２へ飛ぶ</p></a>
      <a href="#third" @click="returnScroll(3)"><p>３へ飛ぶ</p></a>
      <a href="#ford" @click="returnScroll(4)"><p>４へ飛ぶ</p></a>
      <a href="#five" @click="returnScroll(5)"><p>５へ飛ぶ</p></a>
    </div>
    <!-- idをrefとして指定してる点に注意↓ -->
    <div class="test" ref="fast">Hello world1</div>
    <div class="test" ref="second">Hello world2</div>
    <div class="test" ref="third">Hello world3</div>
    <div class="test" ref="ford">Hello world4</div>
    <div class="test" ref="five">Hello world5</div>
    <button @click="returnScroll(6)">TOPに戻る</button>
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
    returnScroll(value) {
      console.log(value)
      if(value == 1){
        window.scrollTo({
          top: this.fastDiv.y,
          behavior: 'smooth'
        })
      } else if(value == 2){
        window.scrollTo({
          top: this.secondDiv.y,
          behavior: 'smooth'
        })
      } else if(value == 3){
        window.scrollTo({
          top: this.thirdDiv.y,
          behavior: 'smooth'
        })
      } else if(value == 4){
        window.scrollTo({
          top: this.fordDiv.y,
          behavior: 'smooth'
        })
      } else if(value == 5){
        window.scrollTo({
          top: this.fiveDiv.y,
          behavior: 'smooth'
        })
      } else if(value == 6){
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        })
      }
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