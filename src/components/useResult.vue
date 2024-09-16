<template>
    <h4>{{ rank }}</h4>
  <p> Reaction-Time: {{ score }}ms</p>
</template>

<script>
export default {
    props:['score'],
    data(){
        return{
            rank:null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank="You proved you're hattori Student"
        }
        else if (this.score < 400){
            this.rank="Are you winning?"
        }
        else{
            this.rank='Snail life...'
        }
    }

}
</script>

<style scoped>
p,h4{
    color: #25e628;
    font-weight: 700;
}
</style>