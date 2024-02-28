<template>
  <h1>{{ Wallet_title }}</h1>
  <button>点击钱包</button>
  <van-button type="success">成功按钮</van-button>
  <van-button type="primary">主要按钮</van-button>
  <van-button type="success">成功按钮</van-button>
  <van-button type="default">默认按钮</van-button>
  <van-button type="warning">警告按钮</van-button>
  <van-button type="danger">危险按钮</van-button>

</template>

<script setup>
  import { ref } from 'vue';
  import Web3 from 'web3';
  const Wallet_title = ref('Wallet');
  
  // 实例化Web3
  var web3 = new Web3(Web3.givenProvider || "wss://sepolia.infura.io/ws/v3/d82e57138b8f43d791ff7be7137bd914")
  console.log(web3);
</script>

<style lang="less">
h1 {
  color: pink;
  font:50px/1.5 'Microsoft YaHei';
}
</style>

