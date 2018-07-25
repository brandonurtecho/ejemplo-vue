<template>
    <div>
      <h1>Heroes</h1>  
      <div class="sorting">
        <label for="filtername">Find your hero:</label>
        <input v-model="findName" id="filtername" type="text" />
      </div>    
      <ul>
        <li v-for="name in filteredNames" :key="name">
          {{ name }}
        </li>
      </ul>
    </div>    
</template>

<script>
export default {
  name: "Example",
  data() {
    return {
      findName: "",
      names: [
        "Evan You",
        "John Lindquist",
        "Jen Looper",
        "Miriam Suzanne",
        "Chris Coyier",
        "Geoff Graham",
        "Divya Sasidharan",
        "Lea Verou",
        "Rachel Andrew",
        "Vitaly Friedman",
        "Ryan Florence",
        "Dan Abramov",
        "Jen Simmons",
        "Robin Rendle",
        "Nicole Sullivan"
      ]
    };
  },
  computed: {
    filteredNames() {
      let filter = new RegExp(this.findName, "i");
      console.log("hola");
      return this.names.filter(el => el.match(filter));
    }
  }
};
</script>


<style>
</style>
