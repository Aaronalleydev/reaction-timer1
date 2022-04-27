<template>
  <p>Reaction time: {{ score }}ms</p>
  <p v-if="!isPlaying" class="rank">{{rank}}</p>
</template>

<script>
export default {
 props: [ 'score', 'isPlaying' ],
 data() {
     return{
         rank: null
     }
     
 },
 mounted(){
     if(this.score < 250) {
         this.rank = 'Ninja fingers'
     } else if(this.score < 400){
         this.rank = 'Rapid reflexes'
     } else {
         this.rank = 'Snail pace'
     }
 }
}
</script>

<style>
.rank{
    font-size: 1.4em;
    color: lightgreen;
    font-weight: bold;
}
</style>