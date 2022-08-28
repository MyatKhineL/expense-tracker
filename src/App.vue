<template>
  <h1>App</h1>
  <TheHeader></TheHeader>
  <div class="container">
    <CalculateTransaction></CalculateTransaction>
    <TransactionsList :transactions="transactions"></TransactionsList>
    <AddTransaction></AddTransaction>
  </div>

</template>

<script>
import TheHeader from './components/Layouts/TheHeader'
import CalculateTransaction from "@/components/CalculateTransaction";
import TransactionsList from "@/components/TransactionsList";
import AddTransaction from "@/components/AddTransaction";
export default {
  name: 'App',
  components:{
    AddTransaction,
    TransactionsList,
    CalculateTransaction,
    TheHeader
  },
  data(){
    return{
      transactions:[
        {
          id:1,
          name:"Cash",
          amount:-40000
        },
        {
          id:2,
          name:"Salary",
          amount:6000
        },
        {
          id:3,
          name:"Computer",
          amount:-100
        },

      ]
    }
  }

}
</script>


