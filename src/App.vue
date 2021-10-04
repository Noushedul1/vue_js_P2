<template>
<div>
  <Model />
  <h1>{{ title }}</h1>
  <h4>{{ msg }}</h4>
  <p>{{ hobby[0] }}</p>
  <p>{{ myObj.fname }}</p>
  <p>{{ myname() }}</p>
  <img v-bind:src="src" :alt="alt">
  <img src="./assets/logo.png" alt="">
  <p><a :href="link">Google</a></p>
  <p v-text="myText"></p>
  <p v-html="myHtml"></p>
  <input type="text" ref="name">
  <button @click="handleClick">Click Here</button>
  <Model />
  <Cons />
  <p v-if="yourAge == allowedAge">
    You are good to go.
  </p>
  <p v-else-if="yourAge <= allowedAge">
    ohh you can go there....
  </p>
  <p v-else>
    you ar not allowed!
  </p>
  <hr>
  <p v-show="yourName == 'Arman' ">
    You can access now Arman>>>
  </p>
  <p v-show="yourName !== 'Arman'">
    You cannot access here....
  </p>
  <div v-if="ourCountry()">
    Our counrty name is Bangladesh
  </div>
  <div v-else>
    Ohh sorry ...
  </div>
  <div>
    <h1>{{yourName}}</h1>
    <h2 v-once>{{yourName}}</h2>
    {{update()}}
  </div>
  <div v-on:mousemove="valueChange" class="vOn">
    Hover Me
  </div>
  <p>X : {{x}}</p>
  <p>Y : {{y}}</p>

  <div>
    <p>{{user}}</p>
    <button v-on:click="updateName('Southern',$a)">Click Here</button>
  </div>
  
  <div>
    <form v-on:submit.prevent="handleForm">
      <input type="text">
      <input type="submit" value="Submit">
    </form>
  </div>

  <div class="formdata">
    <form v-on:submit.prevent="ourdata">
      <label>First name: </label>
      <input type="text" v-model="myformData.alaName">
      <hr>
      <label>Last name: </label>
      <input type="text" v-model="myformData.secondName">
      <hr>
      <input type="submit">
    </form>
  </div>
  
  <div>
    <button @click="a++">Add A</button>
    <button @click="b++">Add B</button>
    <p>A = {{a}}</p>
    <p>B = {{b}}</p>
    <p>salary + A = {{addA}}</p>
    <p>salary + B = {{addB}}</p>
    
  </div>
  <p v-for="al in myarr" :key="al">{{al}}</p>
  <ComHeader :newArra="country"/>
  <ComUlli :mypropsName="students"/>
  </div>
</template>

<script>
import Model from './components/Model.vue';
import Cons from './components/Cons.vue';
import ComHeader from './components/Header.vue';
import ComUlli from './components/Ulli.vue';
export default {
  name: 'App',
  components: { Model,Cons,ComHeader,ComUlli},
  data () {
    return {
      title: 'This is my first vue app :)',
      msg: 'Our country name is Bangladesh',
      hobby: ['cricket','football'],
      myObj: {
        fname: 'Khan',
        age: 24
      },
      src: 'https://picsum.photos/id/1/200/300',
      alt: 'This is lorem Picsum',
      link: 'https://www.google.com/',
      myText: 'Hello CSE Engineer',
      myHtml: '<strong>SOUTHERN UNIVERSITY</strong>',
      yourAge: 17,
      allowedAge: 18,
      yourName: 'Arman',
      country: 'Bangladesh',
      x: 0,
      y: 0,
      user: 'Akib',
      myformData: {
        alaName: '',
        secondName: ''
      },
      a: 0,
      b: 0,
      salary: 10,
      myarr: ['a','b','c'],
      students: ['akib','aki','shaki','mohima','arman']
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.fucus();
    },
    myname() {
      return 'noushed';
    },
    ourCountry() {
      return this.country == 'England' ? true : false;
    },
    update() {
      setTimeout(()=>{
        this.yourName = 'Rakibul Hasan Arman';
      },2000);
    },
    valueChange(event) {
      this.x = event.clientX;
      this.y = event.clientY;
    },
    updateName(newname,a) {
      this.user = newname;
      console.log(a);
    },
    handleForm() {
      console.log('Form is submitted');
    },
    ourdata() {
      console.log(this.myformData);
    }
  },
  computed: {
     addA() {
      console.log('add A');
      return this.salary + this.a;
    },
     addB() {
      console.log('add B');
      return this.salary + this.b;
    }
  }
}
</script>

<style scoped>
body{
  font-family: 'Noto Sans Display', sans-serif;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid black;
}
h4{
  color: red;
}
.vOn{
  height: 100px;
  width: 100px;
  background: red;
}
</style>
