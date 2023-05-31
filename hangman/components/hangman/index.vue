<template>
   <div class="hangman-wrapper">
      <h1>Use the alphabet below to guess the word.</h1>
      <div class="alphabet-words">
         <input type="button" class="alphabet-button" v-for="(alphabet, index) in alphabets" :key="index" :id="alphabet" :value="alphabet" @click="alphabetButton" />
      </div>
      <div class="hangman-box-wrapper">
         <div class="display-main-word-wrapper">
            <p class="display-main-word">{{ mainWord[0] }}</p>
            <p class="display-main-word">{{ mainWord[1] }}</p>              
            <p class="display-main-word">{{ mainWord[2] }}</p>             
            <p class="display-main-word">{{ mainWord[3] }}</p>              
            <p class="display-main-word">{{ mainWord[4] }}</p>               
            <p class="display-main-word">{{ mainWord[5] }}</p>              
            <p class="display-main-word">{{ mainWord[6] }}</p>             
            <p class="display-main-word">{{ mainWord[7] }}</p>   
         </div>
         <div class="hangman-box">
            <div class="hangman-shape-wrapper">
               <div class="hangman-shape item-one" v-if="itemOne"></div>
               <div class="hangman-shape item-two" v-if="itemTwo"></div>
               <div class="hangman-shape item-three" v-if="itemThree"></div>
               <div class="hangman-shape item-four" v-if="itemFour"></div>
               <div class="hangman-shape item-five" v-if="itemFive"></div>
               <div class="hangman-shape item-six" v-if="itemSix"></div>
               <div class="hangman-shape item-seven" v-if="itemSeven"></div>
               <div class="hangman-shape item-eight" v-if="itemEight"></div>
            </div>
         </div>
      </div>
      <div class="win-wrapper" v-if="win">
         <h2>Congratulation! You Won</h2>
         <p class="correct-word">
            Correct Word: <strong style="color: #4099B7;">{{ mainWord[0] }}{{ mainWord[1] }}{{ mainWord[2] }}{{ mainWord[3] }}{{ mainWord[4] }}{{ mainWord[5] }}{{ mainWord[6] }}{{ mainWord[7] }}</strong>
         </p>
         <input type="button" class="play-again-button" value="Play Again" @click="playAgain" />
      </div>
      <div class="lose-wrapper" v-if="lose">
         <h2>unfortunately! You Lose</h2>
         <p class="correct-word">
            Correct Word was: <strong style="color: #4099B7;">{{ selectedWord }}</strong>
         </p>
         <input type="button" class="play-again-button" value="Play Again" @click="playAgain" />
      </div>
   </div>
</template>

<script setup lang="ts">
const alphabets = ref(['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R',  'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'])
const mainWord = ref(['_', '_', '_', '_', '_', '_', '_', '_',]) as any
const wrongWord = ref([]) as any
const selectedWord = ref('ABCDEFGH') as any
const selectedWordArray = ref(selectedWord.value.split(""))
const win = ref(false) as any
const lose = ref(false) as any
const itemOne = ref(false) as any
const itemTwo = ref(false) as any
const itemThree = ref(false) as any
const itemFour = ref(false) as any
const itemFive = ref(false) as any
const itemSix = ref(false) as any
const itemSeven = ref(false) as any
const itemEight = ref(false) as any


function alphabetButton(value:any){
   console.log("🚀 ~ file: index.vue:66 ~ alphabetButton ~ value.target.value:", value.clicked)
   if(value.target.value === selectedWordArray.value[0]){
      mainWord.value[0] = value.target.value    
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[1]){
      mainWord.value[1] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[2]){
      mainWord.value[2] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[3]){
      mainWord.value[3] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[4]){
      mainWord.value[4] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[5]){
      mainWord.value[5] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[6]){
      mainWord.value[6] = value.target.value  
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else if(value.target.value === selectedWordArray.value[7]){
      mainWord.value[7] = value.target.value
      console.log("🚀 ~ file: index.vue:57 ~ alphabetButton ~ mainWord.value:", mainWord.value.length)
      if (mainWord.value[0] === selectedWord.value[0] && mainWord.value[1] === selectedWord.value[1] && mainWord.value[2] === selectedWord.value[2] && mainWord.value[3] === selectedWord.value[3] && mainWord.value[4] === selectedWord.value[4] && mainWord.value[5] === selectedWord.value[5] && mainWord.value[6] === selectedWord.value[6] && mainWord.value[7] === selectedWord.value[7]){
         win.value = true
      }
   } else {
      wrongWord.value.push(value.target.value)
      if(wrongWord.value.length === 9){
         lose.value = true
      }
   }

   if(wrongWord.value.length === 1){
      itemOne.value = true
   } else if(wrongWord.value.length === 2) {
      itemTwo.value = true
   } else if(wrongWord.value.length === 3) {
      itemThree.value = true
   } else if(wrongWord.value.length === 4) {
      itemFour.value = true
   } else if(wrongWord.value.length === 5) {
      itemFive.value = true
   } else if(wrongWord.value.length === 6) {
      itemSix.value = true
   } else if(wrongWord.value.length === 7) {
      itemSeven.value = true
   } else if(wrongWord.value.length === 8) {
      itemEight.value = true
   }
}

function playAgain() {
   location.reload()
}
</script>

<style lang="scss">
@import '@/assets/scss/global.scss';
.hangman-wrapper{
   margin-top: 80px;
   text-align: center;
   position: relative;
}

.alphabet-words{
   margin: 60px 0px;
   width: 100%;
   display: flex;
   flex-direction: row;
   flex-wrap: wrap;
   justify-content: space-between;
   align-items: center;
   
   input{
      border: 1px solid $primary;
      outline: none;
      border-radius: 8px;
      font-size: 20px;
      color: $primary;
      width: 40px;
      height: 40px;
      &:active {
         background: $primary;

      }
      &:hover {
         background: $primary;
         color: #fff;
      }
   }
}

.hangman-box-wrapper {
   width: 100%;
   margin: 90px 0px;
   display: flex;
   flex-direction: row;
   justify-content: space-evenly;
   align-items: center;
   
   .display-main-word-wrapper{
      flex-basis: 15%;
      display: flex;
      flex-direction: row;
      justify-content: space-between;

      .display-main-word{
         margin-right: 4px;
         font-size: 36px;
         margin: 60px 0px 30px;
      }
   }

   .hangman-box {
      flex-basis: 50%;
      border: 3px dotted $primary;
      max-width: 400px;
      min-height: 400px;
      border-radius: 8px;
   }  
}

.hangman-shape-wrapper{
   width: 100%;
   position: relative;
   padding: 60px 60px;
   .hangman-shape {
      display: block;
   }
   .item-one {
      position: absolute;
      top: 330px;
      width: 280px;
      height: 10px;
      border-bottom: 3px solid black;
   }
   .item-two {
      width: 10px;
      height: 280px;
      border-left: 3px solid black;
   }
   .item-three {
      position: absolute;
      width: 180px;
      height: 10px;
      top: 50px;
      border-bottom: 3px solid black;
   }
   .item-four {
      position: absolute;
      width: 10px;
      height: 20px;
      top: 60px;
      right: 230px;
      border-left: 3px solid black;
   }
   .item-five {
      position: absolute;
      width: 40px;
      height: 40px;
      top: 80px;
      right: 218px;
      border-radius: 50%;
      border: 3px solid black;
   }
   .item-six {
      position: absolute;
      width: 10px;
      height: 75px;
      top: 120px;
      right: 230px;
      border-left: 3px solid black;
   }
   .item-seven {
      position: absolute;
      width: 40px;
      height: 40px;
      top: 140px;
      right: 219px;
      border-left: 3px solid black;
      border-top: 3px solid black;
      transform: rotate(45deg);
   }
   .item-eight {
      position: absolute;
      width: 40px;
      height: 40px;
      top: 200px;
      right: 219px;
      border-left: 3px solid black;
      border-top: 3px solid black;
      transform: rotate(45deg);
   }
}

.win-wrapper {
   width: 100%;
   min-height: 100%;
   padding: 200px 0px;
   background: #fff;
   border:5px dotted $primary;
   position: absolute;
   top: 0;
   left: 0;
   border-radius: 15px;
   h2{
      font-size: 64px;
      color: $success;
      margin: 30px;
   }
   .correct-word{
      font-size: 32px;
      color: #000;
   }
}

.lose-wrapper {
   width: 100%;
   min-height: 100%;
   padding: 200px 0px;
   background: #fff;
   border:1px solid $primary;
   position: absolute;
   top: 0;
   left: 0;
   border-radius: 15px;
   h2{
      font-size: 64px;
      color: $danger;
      margin: 30px;
   }
   .correct-word{
      font-size: 32px;
      color: #000;
   }
}

.play-again-button {
   border: 1px solid $primary;
   outline: none;
   border-radius: 8px;
   font-size: 20px;
   color: $primary;
   padding: 10px 15px;
   margin-top: 40px;
   &:hover {
      background: $primary;
      color: #fff;
   }
}
</style>