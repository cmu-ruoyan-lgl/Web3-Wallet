---
marp: true
---

# web3 学习笔记

## 钱包

热钱包 HotWallet（联网的在线钱包）
冷钱包 Cold Wallet（脱离网络环境的离线钱包）
生成、存储、签名
只存账户 真正的资产是存在链上

## MetaMask

助记词、私钥（登录）
不在以太坊主网开发 去测试网（Goerli）
可以创建多个账号（每个网络） 每个账号都有一个私钥 可以通过私钥 倒入账号

### Goerli

    获取eth需要挖矿
    网址：https://goerli-faucet.pk910.de/
    网址：https://www.tokenpocket.pro/

## 智能合约（DApp）

去中心化的 App
以太坊的智能应用程序，某些约定的情况下去发布 用户按照约定的规则去使用程序
分布式的应用开发
技术栈 web3 全栈开发 solidity

## 搭建 vue 项目

安装依赖
web3 bip39 ethereumjs-tx@1.3.7 ethereumjs-util ethereumjs-wallet

## web3js

npm i web3
用前端变成工具与 eth 进行交互
用 web3 去连接 eth 的 RPC 层 || 暴露的 RPC 接口的节点
web3 js 的包
web3.eth：用于与以太坊区块链和智能合约之间的交互。

web3.utils：包含一些辅助方法。

web3.shh：用于协议进行通信的 P2P 和广播。

web3.bzz：用于与群网络交互的 Bzz 模块。

打开 infura 网站地址：https://infura.io/dashboard，使用邮箱注册后登陆
163 邮箱

web3 的高频 API ：

1.创建账号：
web3.eth.accounts.create([entropy])

使用ethereumjs-tx@1.3.7
需要一个垫片 vue.config.js
const NodePolyfillWebpackPlugin = require("node-polyfill-webpack-plugin");

- [bip39](https://github.com/bitcoinjs/bip39)：随机产生新的 mnemonic code，并可以将其转成 binary 的 seed。
- [ethereumjs-wallet](https://github.com/ethereumjs/ethereumjs-wallet)：生成和管理公私钥，下面使用其中 hdkey 子套件来创建 HD 钱包。
- [ethereumjs-util](https://github.com/ethereumjs/ethereumjs-util)：Ethereum 的一个工具库。


在BIP32路径中定义以下5个级别：
m/purpse'/coin_type'/account'/change/address_index

- purpose：在BIP43之后建议将常数设置为44'。表示根据BIP44规范使用该节点的子树。
- Coin_type：币种，代表一个主节点（种子）可用于无限数量的独立加密币，如比特币，Litecoin或Namecoin。此级别为每个加密币创建一个单独的子树，避免重用已经在其它链上存在的地址。开发人员可以为他们的项目注册未使用的号码。
- Account：账户，此级别为了设置独立的用户身份可以将所有币种放在一个的帐户中，从0开始按顺序递增。
- Change：常量0用于外部链，常量1用于内部链，外部链用于钱包在外部用于接收和付款。内部链用于在钱包外部不可见的地址，如返回交易变更。
- Address_index：地址索引，按顺序递增的方式从索引0开始编号。

BIP44的规则使得 HD钱包非常强大，用户只需要保存一个种子，就能控制所有币种，所有账户的钱包，因此由BIP39 生成的助记词非常重要，所以一定安全妥善保管，那么会不会被破解呢？如果一个 HD 钱包助记词是 12 个单词，一共有 2048 个单词可能性，那么随机的生成的助记词所有可能性大概是`5e+39`，因此几乎不可能被破解。

keyStore就是JSON字符串


async function async1() {
  console.log("acync1 start");
  await async2();
  console.log("async1 end");
}
async function async2() {
  console.log("acync2");
}
console.log("start");
setTimeout(() => {
  console.log("settimeout");
}, 0);
async1();
console.log("processing");
new Promise((resolve, reject) => {
  for (let i = 0; i <= 2; i++) {
    console.log(i);
    resolve();
  }
})
  .then(function () {
    console.log("promise1");
  })
  .then(function () {
    console.log("promise2");
  });
console.log("end");
const seedForm = ref({
  toAddress: "",
  price: "",
  pwd: "",
});