/* eslint-disable no-unused-vars */
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

import eventBus from '../Servises/eventBus.js'
 export default {
      name:"Followers",
       props:["followers"],
     methods: {
         sendFollower(id){
             eventBus.$emit("ToRemoveFollower",id)
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