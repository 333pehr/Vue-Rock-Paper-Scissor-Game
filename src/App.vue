<template>
  <div>
    <h2 class="title">Rock &nbsp; Paper &nbsp; Scissor</h2>
  </div>
  <div class="container">
    <div class="select">
    <div class="box">
      <div class="rock" @click="userCheck('Rock')">
        <img src="../assets/noun-fist-edited.png" alt="ROCK" width="100"
        height="100">
      </div>
      <span>Rock</span>
    </div>
    <div class="box">
      <div class="paper" id="PAPER" @click="userCheck('Paper')">
        <img src="../assets/noun-wave-edited.png" alt="PAPER" width="100"
        height="100">
        </div>
      <span>Paper</span>
    </div>
    <div class="box">
      <div class="scissor" id="SCISSOR" @click="userCheck('Scissor')">
        <img src="../assets/noun-scissors-edited.png" alt="SCISSOR" width="100"
        height="100">
      </div>
      <span>Scissor</span>
    </div>
    </div>
  </div>
  <div class="result">
    <h2 :class="{
      'win': text =='WIN',
      'lose': text =='LOSE',
      'draw': text =='DRAW'
    }">{{text}}</h2>
    <h3 v-if="computerChose">opponent chose {{computerChose}}</h3>
    <h4> win &nbsp;&nbsp; draw &nbsp;&nbsp; lose </h4>
    <h2> {{win}} : {{draw}} : {{lose}}</h2>
  </div>
  <div class="createdBy">
    <div class="programmer">
      <a href="https://github.com/333pehr" target="_blank">GitHub</a>
      <span>
        Sepehr Latifi Azad
      </span>
      <a href="https://www.linkedin.com/in/sepehrlatifiazad" target="_blank">LinkedIn</a>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      win: 0,
      lose: 0,
      draw: 0,
      computerChose: '',
      userSelect: '',
      text: '',
      showText: true,
    }
  },
  methods: {
    computerSection(){
      let random = Math.random();
      if(random <= 0.333){
        this.computerChose = 'Rock';
      }
      else if(random > 0.333 && random <= 0.666){
        this.computerChose = 'Paper';
      }
      else{
        this.computerChose = 'Scissor';
      }
    },
    userCheck(select){
      this.computerSection();
      if(this.computerChose === select){
        this.text = 'DRAW';
        this.draw ++;
      }
      else if( (this.computerChose === 'Rock' && select === 'Paper') ||
               (this.computerChose === 'Scissor' && select === 'Rock') ||
               (this.computerChose === 'Paper' && select === 'Scissor')){
        this.text = 'WIN';
        this.win ++;
      }
      else{
        this.text = 'LOSE';
        this.lose ++;
      }
    }
  }
}
</script>

<style>
@media only screen and (max-width: 1000px) {
  img{
    width: 100px;
    height: 100px;
  }
  #app {
  font-family:'Times New Roman', Times, serif;
  text-align: center;
  color: white;
  margin-top: 10px;
  }
  .title {
  letter-spacing: 2px;
  padding: 6px;
  border-bottom: 1px solid #bdbdbd;
  border-top: 1px solid #bdbdbd;
  width: 90%;
  margin: 0 auto;
}
.container{
  background-color: rgba(0, 0, 0, 0.3);
  border: 3px solid white;
  border-radius: 10px;
  width: 70%;
  margin: 0 auto;
  margin-top: 40px;
  display: flex;
}
.select{
  margin: 0 auto;
}
.box{
  margin-bottom: 25px;
}
.box span{
  font-size: 20px;
}
.rock{
  background-color: white;
  border-radius: 250px;
  margin: 15px 25px;
  transition: 500ms;
}
.rock:hover{
  background-color: #D32F2F;
  cursor: pointer;
  rotate: -10deg;
}
.paper{
  background-color: white;
  border-radius: 250px;
  margin: 0 25px;
  margin-bottom: 15px;
  transition: 500ms;
}
.paper:hover{
  background-color: #388E3C;
  cursor: pointer;
  rotate: 5deg;
}
.scissor{
  background-color: white;
  border-radius: 250px;
  margin: 0 25px;
  margin-bottom: 15px;
  transition: 500ms;
}
.scissor:hover{
  background-color: #FDD835;
  cursor: pointer;
  rotate: 10deg;
}
.result{
  margin-bottom: 50px;
}
.win{
  color: #388E3C;
}
.lose{
  color:#D32F2F;
}
.draw{
  color: #FDD835;
}
.programmer{
  width: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  display: inline-flexbox;
  position: fixed;
  bottom: 0px;
  text-align: center;
  height: 40px;
  padding-top: 10px;
  margin: 0 auto;
  left: 0px;
}
.programmer span{
  color: #ffffff;
  margin: 0 25px;
  font-size: 20px;
}
.programmer a{
  color: #BDBDBD;
}
}
@media only screen and (min-width: 1001px) {
  img{
    width: 200px;
    height: 200px;
  }
  #app {
  font-family:'Times New Roman', Times, serif;
  text-align: center;
  color: white;
  margin-top: 50px;
  }
  .title {
  letter-spacing: 2px;
  padding: 10px;
  border-bottom: 2px solid #bdbdbd;
  border-top: 2px solid #bdbdbd;
  width: 30%;
  margin: 0 auto;
}
.container{
  background-color: rgba(0, 0, 0, 0.3);
  border: 3px solid white;
  border-radius: 10px;
  width: 70%;
  margin: 0 auto;
  margin-top: 100px;
  padding: 50px 25px;
}
.select{
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin: 0 auto;
}
.box span{
  font-size: 24px;
  letter-spacing: 0.7px;
}
.rock{
  background-color: white;
  border-radius: 250px;
  margin: 15px 0px;
  transition: 500ms;
}
.rock:hover{
  background-color: #D32F2F;
  cursor: pointer;
  rotate: -10deg;
}
.paper{
  background-color: white;
  border-radius: 250px;
  margin: 15px 0px;
  transition: 500ms;
}
.paper:hover{
  background-color: #388E3C;
  cursor: pointer;
  rotate: 5deg;
}
.scissor{
  background-color: white;
  border-radius: 250px;
  margin: 15px 0px;
  transition: 500ms;
}
.scissor:hover{
  background-color: #FDD835;
  cursor: pointer;
  rotate: 10deg;
}
.result{
  margin-top: 110px;
}
.result h2{
  font-size: 30px;
}
.win{
  color: #388E3C;
}
.lose{
  color:#D32F2F;
}
.draw{
  color: #FDD835;
}
.programmer{
  width: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  display: inline-flexbox;
  position: fixed;
  bottom: 0px;
  text-align: center;
  height: 40px;
  padding-top: 10px;
  margin: 0 auto;
  left: 0px;
}
.programmer span{
  color: #ffffff;
  margin: 0 25px;
  font-size: 20px;
}
.programmer a{
  color: #BDBDBD;
}
}

</style>
