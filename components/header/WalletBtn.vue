<template>
    <div class="container">
        <!-- after wallet connected BTN -->
        <div class="droppBtn" v-if="isConnect" @mouseover="upHere = true">
            <img src="../../asset/profile.png" alt="profile">
            <span>{{web3.coinbase}}</span>
            <img src="../../asset/9.png" alt="dropdown">
        </div>
        <!-- Droppdown -->
        <div class="droppBox" v-show="upHere" @mouseover="upHere = true" @mouseleave="upHere = false">
            <div class="boxData">
                <img src="../../asset/profile.png" alt="profile">
                <span>My Profile</span>
            </div>
            <div class="boxData">
                <img src="../../asset/profile.png" alt="profile">
                <span>Change Wallet</span>
            </div>
            <a class="boxData" href="/">
                <img src="../../asset/Arrow Right.png" alt="profile">
                <span>Logout</span>
            </a>
        </div>

        <!-- wallet Connect BTN -->
        <div class="ConnectBtn" @click="isConnect = !isConnect , isShow = !isShow" v-if="!isConnect " >
            <img src="../../asset/Wallet.png" alt="wallet" />
            <span>Connect wallet</span>
        </div>
        <transition name="fade" appear>
            <div class="btnWrraper" v-if="isShow" @click="isHide = !isHide">
                    <metamask id="metamask" @connect="initWeb3" v-if="isHide"/>
                    <wallet-connect  v-if="isHide"/>
            </div>
        </transition>
    </div>
</template>

<script>
import Web3 from 'web3'
import { mapGetters, mapMutations } from 'vuex'
import Metamask from './Metamask.vue'
import WalletConnect from './WalletConnect.vue'


    export default {
        name:"WalletBTN",
        components: {
            Metamask,
                WalletConnect
        },

        data() {
            return {
                isConnect: false,
                isShow: false,
                isHide: true,
                upHere: false,
                errorMessage: '',
            }
        },
        
        computed: {
            ...mapGetters('web3', ['getInstance']),
            web3 () {
                return this.getInstance
            }
        },

        methods: {
            ...mapMutations('web3', ['registerWeb3Instance']),
            async initWeb3 () {

                // check for web3 provider
                if (typeof window.ethereum !== 'undefined'){
                    try {
                        // Ask to connect
                        await window.ethereum.send('eth_requestAccounts');
                        const instance = new Web3(window.ethereum)

                        // Get necessary info on node
                        const networkId = await instance.eth.net.getId();
                        const coinbase = await instance.eth.getCoinbase();
                        const balance = await instance.eth.getBalance(coinbase);

                        // Save it to store
                        this.registerWeb3Instance({
                            networkId,
                            coinbase,
                            balance
                        });
                        this.errorMessage = '';
                    } catch (error) {
                        // user denied account aceest
                        console.error('user denied web3 access', error);
                        window.alert("User denie to connect Metamask Wallet! Reconnect the Metamsk Wallet.")
                        this.errorMessage = 'Please connect to your Ethereum address on Metamask before connecting to this website';
                        return;
                    }
                }
                // No web3 Provider
                else {
                    console.error('No Web3 provider detected');
                    this.errorMessage = "No web3 provider detected. Did you install the Metamask extension on this browser?";
                    return;     
                }
            },
        }
    }
</script>

<style scoped>
.container {
    margin-right: 20px;
    display: flex;
    /* position: relative; */
    transition: all 1s ease-in-out;
}



.droppBtn {
    display: flex;
    align-items: center;
    background: linear-gradient(222.94deg, #32C5FF 0%, #B620E0 45.93%, #FFAA12 86.01%);
    border-radius: 90px;
    padding: 12px 28px;
    cursor: pointer;
}

.droppBtn:hover {
    background: linear-gradient(222.94deg, #32C5FF90 0%, #B620E090 45.93%, #FFAA1290 86.01%);
    transition: all 0.3s ease-in-out;
}

.droppBtn span , .droppBtn img{
    background:transparent;
}
.droppBtn img{
    width: 28px;
    height: 28px;
}
.droppBtn img:nth-child(3){
    width: 14px;
    height: 10px;
}
.droppBtn span{
    font-family: 'Inter';
font-style: normal;
font-weight: 600;
font-size: 14px;
line-height: 20px;
margin-left: 8px;
margin-right: 8px;
}

.droppBox{
    width: 198px;
    position: absolute;
    top: 88px;
    box-shadow: 0px 16px 64px -48px rgba(31, 47, 70, 0.15);
    border-radius: 12px;
    background: #23262F;
    display: flex;
    flex-direction: column;
}

.boxData:nth-child(2){
    border-top: 1px solid #353945;
    border-bottom: 1px solid #353945;
}
.boxData{
    display: flex;
    align-items: center;
    padding-top: 21px;
    padding-bottom: 21px;
    padding-left: 14px;
    background:transparent;
    cursor: pointer;
    text-decoration: none;
}
.boxData img{
    width: 22px;
    height: 22px;
    background:transparent;
}

.boxData span{
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    color: #777E90;
    margin-left: 14px;
    background:transparent;
    width: 100%;
    height: 100%;
}

.boxData span:hover{
    color: #fff;
}

.ConnectBtn{
    display: flex;
    align-items: center;
    padding: 14px 28px;
    background: linear-gradient(222.94deg, #32C5FF 0%, #B620E0 45.93%, #FFAA12 86.01%);
    border-radius: 90px;
    cursor: pointer;
}

.ConnectBtn:hover {
    background: linear-gradient(222.94deg, #32C5FF90 0%, #B620E090 45.93%, #FFAA1290 86.01%);
    transition: all 0.3s ease-in-out;
}

.ConnectBtn img {
    background:transparent;
    margin-right: 8px;
    width: 24px;
    height: 24px;
}
.ConnectBtn span {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 17px;
    background:transparent;
}
.btnWrraper{
    position: absolute;
    top: 50%;
    left: 45%;
    border: 1px solid rgb(75, 71, 71);
    border-radius: 12px;
    background: #23262F;
}
#metamask {
    background:transparent;
}

.fade-enter-active,
.fade-leave-active {
  transition: all .3s ease-in-out;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

</style>