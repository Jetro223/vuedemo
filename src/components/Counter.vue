<template>
  <div>
    <p>Ich bin ein Counter</p>
    <p>
      <input v-model="secondcount" type="text" />
    </p>
    <p>{{count}} - Plus eins wäre: {{countplusone}}</p>

    <p>Mein zweiter Count ist: {{secondcount}}</p>
    <p>
      <button @click="increment()">Increment</button>
      <button @click="decrement()">Decrement</button>
    </p>

    <div>
      <button @click="add()">Add to array</button>
    </div>

    <div>
      <ul>
        <li v-for="item in myarray">{{item.name}} - Schuhgröße {{item.schuhgroesse}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Counter",
  props: {},
  data: function() {
    return {
      count: 0,
      secondcount: 0,
      myarray: [
        { name: "Michael", schuhgroesse: 43 },
        { name: "Axel", schuhgroesse: 45 }
      ]
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    },
    add() {
      this.myarray.push({ name: "neu", schuhgroesse: this.count });
    }
  },
  computed: {
    countplusone() {
      return this.count + 1;
    }
  },
  created: function() {
    console.log("created");
    this.count = 12;
  },
  mounted: function() {
    console.log("counter has been mounted");
  }
};
</script>


<style scoped lang="scss">
</style>
