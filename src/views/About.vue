<template>
  <div>
    <h2> {{ test }} </h2>
    <form @submit.prevent="addname">
      <input type="text" placeHolder="Name" v-model="name"/>
      <button @click="addName">Submit</button>
    </form>
    <br />
    <div :key="ind" v-for="(person, ind) in admin">
      <span v-if="person.name[0] === 'S'">{{ person.name }}</span>
      <h1 :class="person.name[0] === 'L' ? 'red' : 'blue'" v-else> {{ person.name }} </h1>
    </div>
    <h2> {{ name }} </h2>
    <!-- <div v-for="(val, prop, ind) in person">
      {{ prop }}: {{ val }}
    </div> -->
  </div>
</template>


<script>
  export default {
    data(){
      return {
        test: 'This is Spencer\'s test',
        admin: [
          {name: 'Shea'},
          {name: 'Shanelle'},
          {name: 'Spencer'},
          {name: 'Logan'}
        ],
        person: {
          name: 'Spencer',
          age: 27,
          food: 'none'
        },
        name: ''
      }
    
    },
    methods: {
      addName(){
        this.admin.push({name: this.name})
        this.name = ''
      }
    }
  }

</script>


<style>
.red {
  background: red
};
.blue {
  background: blue
};

</style>
