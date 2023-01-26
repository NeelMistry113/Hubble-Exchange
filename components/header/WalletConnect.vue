<template>
    <div class="btn">
        <div class="walletConnect" @click="connect">Wallet-Connect</div>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

    export default {
        name: 'WalletConnectN',
        methods: {
            ...mapActions(['connectWalletConnect']),
            async connect() {
                try {
                    const accounts = await this.connectWalletConnect()
                    console.log(accounts)
                } catch (error) {
                    console.log(error)
                }
            }
        }
    }
</script>

<style scoped>
    .walletConnect{
        font-family: 'Inter', sans-serif;
        font-size: 22px;
        padding: 16px 28px;
        cursor: pointer;
        border-top: 1px solid rgb(75, 71, 71);
        color: rgb(183, 171, 171);
    }
    .walletConnect:hover {
        color: #fff;
    }
</style>