<template>
  <div class="test">
    <input type="text" v-model="title"> <br>
    <h1 v-html="title"></h1>
    <p v-text="user.lastName"></p>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else="showName">NOPE</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Hello World!')">
      Save greeting
    </button>
    <br>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <br>
    <hr>
    <br>
    <label> First Name:</label>
    <input type="text" v-model="user.firstName">
    <br>
    <label> Last Name:</label>
    <input type="text" v-model="user.lastName">
    <br>
    <h3>{{fullName}}</h3>
    <h2>{{msg}}</h2>
    </div>
</template>


<script>
 export default{
   name: 'test',
   props: {
     msg: {
       type: String,
       default: 'Foobar'
     }
   },
   data () {
     return {
       title: '<h1>Hello World!</h1>',
       user: {
         firstName: 'John',
         lastName: 'Doe'
       },
       showName: true,
       items: [
       {title: 'Item One'},
       {title: 'Item Two'},
       {title: 'Item Three'}
       ]
     }
   },
   methods: {
     greet: function (greeting) {
       window.alert(greeting)
     },
     pressKey: function () {
       console.log('pressed')
     },
     enterHit: function () {
       console.log('Hitted Enter')
     }
   },
   computed: {
     fullName: function () {
       return this.user.firstName + '' + this.user.lastName
     }
   }
 }
</script>

<style scoped>

</style>
