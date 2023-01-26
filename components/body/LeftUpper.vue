<template>
    <div class="LUContainer">
        <div class="data">
            <p>Index price</p>
            <p>$3841.72</p>
        </div>
        <div class="line"></div>
        <div class="data">
            <p>Markprice</p>
            <p>$2,297.76</p>
        </div>
        <div class="line"></div>
        <div class="data">
            <p>Open interest</p>
            <p>2 ETH</p>
        </div>
        <div class="line"></div>
        <div class="data">
            <p>Open interest</p>
            <p>$4595.52</p>
        </div>
        <div class="line"></div>
        <div class="data">
            <p>24 HOUR CHANGE</p>
            <p>$500.56</p>
        </div>
        <div class="line"></div>
        <div class="data">
            <p>Volume 24h</p>
            <p>$3.73M</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'LeftUpper'
    }
</script>

<style scoped>
.LUContainer{
    height: inherit;
    padding-left: 24px;
    padding-right: 24px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
.line{
    width: 1px;
    height: 40px;
    background-image: linear-gradient(to bottom, #BBBD04, #000000);
}
.data{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    height: inherit;
    width: auto;
}
.data :nth-child(1){
    font-weight: 600;
    font-size: 14px;
    line-height: 15px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: #777E90;
    margin-bottom: 8px;
}
.data :nth-child(2){
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 15px;
    text-align: right;
    color: #FFFFFF;
}
</style>