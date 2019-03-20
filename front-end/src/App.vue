<template>
  <div id="app">
    Amőba
    <table>
      <tr :key="i" v-for="(row,i) in t">
        <td :key="j" v-for="(elem,j) in row" @click="f(i,j)">
          {{elem}}          
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: ()=>({
    next: "X",
    t: Array(10)
          .fill(4)
          .map( () => Array(10).fill(''))
  }),
  methods: {
    f(i,j) {
      this.$set(this.t[i],j,this.next)
      this.next=="X"?this.next="O":this.next="X"
      //console.log(i,j)
    }
  } 
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
td {
  width:20px;
  height:20px;
  border-radius: 3px;
  box-shadow: 1px 1px 3px black;
  padding: 10px;
  cursor: pointer;
}
table {
  text-align: center;
  margin: 0px auto;
  border-spacing: 10px;
  border-collapse: separate;
}
</style>
