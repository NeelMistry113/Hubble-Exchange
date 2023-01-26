<template>
    <div class="LMContainer">
        <div class="heading"><h3>Recent Trades</h3></div>
        <div class="dataHeading">
            <h2>PRICE</h2>
            <h2>SIZE</h2>
            <h2>TIME</h2>
        </div>
        <div class="dataContainer">
            <div class="data">$100</div>
            <div class="data">1</div>
            <div class="data">12:12:50 2/1/2021</div>
        </div>
        
        <div class="dataContainer"></div>
        <div class="dataContainer"></div>
        <div class="dataContainer"></div>
    </div>
</template>

<script>
    export default {
        name:'LeftMid'
    }
</script>

<style scoped>
.LMContainer{
    display: flex;
    flex-direction: column;
    height: inherit;
}
.heading{
    padding: 12px 24px;
    border: 1px solid rgba(255, 255, 255, 0.26);
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    align-items: center;
    letter-spacing: 0.12em;
    text-transform: uppercase;
}
.dataHeading{
    padding: 12px 24px;
    border: 1px solid rgba(255, 255, 255, 0.26);
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
.dataHeading h2{
    font-style: normal;
    font-weight: 700;
    font-size: 12px;
    line-height: 24px;
    align-items: center;
    color: #6E798F;
}
.dataContainer{
    padding: 0px 24px;
    height: 30px;
    border: 1px solid rgba(255, 255, 255, 0.26);
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}
.data{
    padding: auto;
    width: 100%;
    background:transparent;
    font-size: 12px;
}
.dataContainer :nth-child(2){
    display: flex;
    justify-content: center;
}
.dataContainer :nth-child(3){
    display: flex;
    justify-content: flex-end;
}
</style>