<template>
    <div class="container">
        <div class="leftContainer">
            <img src="../../asset/Hubble-Logo.png" alt="HUBBLE">
            <div class="line"></div>
            <navlinks/>
        </div>
        <div class="rightContainer">
            <wallet-btn/>
            <dropdown/>
        </div>
    </div>
</template>

<script>
import Dropdown from './Dropdown.vue'
import Navlinks from './Navlinks.vue'
import WalletBtn from './WalletBtn.vue';
    export default {
  components: {Navlinks, Dropdown, WalletBtn },
        name: 'Navbar'
    }
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 88px;
     background: #141416;
     color: #fff;
}

.leftContainer{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-content: center;
    /* border: 1px solid green; */
    margin-left: 20px;
}

.line{
    border: 1px solid #353945;
    margin-left: 24px;
    margin-right: 24px;
    width: 1px;
    background: #353945;
}

.rightContainer{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-right: 20px;
}

</style>