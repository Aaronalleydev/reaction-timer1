<template>
<div class="scoreboard">
  <p>This is the scoreboard</p>
  <p>1. {{ top }}</p>
  <p>2. {{second}}</p>
  <p>3. {{ third }}</p>
  </div>
</template>

<script>
export default {
    props: [ 'score', ],
    data(){
        return{
            top: 10000,
            second: 5000,
            third: 3000,

        }
    },
    beforeUpdate(){
     if(this.score < this.top) {
         this.top = this.score
     } else if(this.score > this.top && this.score < this.second){
         this.second = this.score
     } else if(this.score > this.second && this.score < this.third) {
         this.third = this.score
     }
 }
}
</script>

<style>

</style>