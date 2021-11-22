<template>
<div>
<ul>
<li v-for="follower in followers" :key="follower.id">
<p>{{follower.name}}</p>
<button @click="sendFollower(follower.id)">remove Followers</button>
<hr>

</li>
</ul>
</div>
</template>
 <script>

 export default {
      name:"Followers",
       props:["followers"],
     methods: {
         sendFollower(id){
             this.$emit("ToRemoveFollower",id)
         },
     },
 };
 </script>
 <style scoped>
  div{
      text-align: center;
      
  }
  li{
      list-style:none;
  }
 </style>