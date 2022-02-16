<template>
  <div class="child">
    {{ money }}
    {{ name }}
    {{ age }}
    <button @click="changeMoney">
      <span>花钱</span>
    </button>
    <button @click="changeAge">
      <span>成长</span>
    </button>
  </div>
</template>

<script>
export default {
  props: ["money","name","age"],
  methods: {
    changeMoney() {
      this.$emit("update:money", this.money - 100);
    },
     changeAge() {
      this.$emit("update:age", this.age + 1);
    },
  },
};
</script>


<style>
.child {
  border: 3px solid green;
}
</style>