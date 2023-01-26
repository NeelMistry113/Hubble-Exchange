<template>
    <div class="RUcontainer">
        <div class="left">
            <img src="../../asset/eth.png" alt="">
            <p>ETH - PERP</p>
        </div>
        <div class="right">
            <img src="../../asset/9.png" alt="">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'RightUpper'
    }
</script>

<style scoped>
.RUcontainer{
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding-left: 22px;
    padding-right: 22px;
}
.left{
    display: flex;
    flex-direction: row;
    align-items: center;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
}
.left img{
    margin-right: 8px;
}
</style>