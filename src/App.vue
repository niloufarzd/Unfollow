<template>
  <div >
  <Followers
   :followers="followers"></Followers>
  </div>
</template>

<script>
import  Followers from './components/Followers'
import eventBus from './Servises/eventBus.js'

export default {
  name: 'App',
  components: {
    Followers,
    },
     data() {
       return {
         followers:[
           {id:12 , name:"ali"},
           {id:14 , name:"hassan"}, 
          {id:16 , name:"fatemeh"},   
          {id:19 , name:"hossein"},    
         {id:10 , name:"sajjad"},
         ],
       };
     },
      methods: {
        ToRemoveFollower(id){
           let FollowerIndex =this.followers.findIndex(
             (follower) =>follower.id == id 
             );
             this.followers.splice(FollowerIndex,1)
        }
      },
       created() {
         eventBus.$on('ToRemoveFollower',data=>{
           this.ToRemoveFollower(data)

         })
         
       },
  };

</script>

<style>
      text-align: center;

</style>
