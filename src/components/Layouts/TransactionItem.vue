<template>
  <li :class="listClass">
      {{transaction.name}} <span>
      {{minusOrPlus}}
      {{Math.abs(transaction.amount)}} ks</span>
    <button class="delete-btn">x</button>
  </li>
</template>
<script>
export default {
  props:["transaction"],
  computed:{
    listClass(){
      return this.transaction.amount > 0 ? 'plus' : 'minus';
    },
    minusOrPlus(){
      return this.transaction.amount > 0 ? '+' : '-';
    }
  }
};
</script>
<style scoped>
li{
  background-color: #fff;
  box-shadow: var(--box-shadow);
  color: #333;
  display: flex;
  justify-content: space-between;
  position: relative;
  padding: 10px;
  margin: 10px 0;
}

li.plus {
  border-right: 5px solid #2ecc71;
}

li.minus {
  border-right: 5px solid #c0392b;
}
.delete-btn {
  cursor: pointer;
  background-color: #e74c3c;
  border: 0;
  color: #fff;
  font-size: 20px;
  line-height: 20px;
  padding: 2px 5px;
  position: absolute;
  top: 50%;
  left: 0;
  transform: translate(-100%, -50%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

li:hover .delete-btn {
  opacity: 1;
}
</style>