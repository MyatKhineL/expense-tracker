<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <transaction-item
    v-for="transaction in transactions"
    :key="transaction.id"
    :transaction="transaction"
    ></transaction-item>
  </ul>
</template>
<script>
import TransactionItem from "@/components/Layouts/TransactionItem";
export default {
  components: {TransactionItem},
  props:['transactions']
}
</script>
<style scoped>
.list {
  list-style-type: none;
  padding: 0;
  margin-bottom: 40px;
}
</style>