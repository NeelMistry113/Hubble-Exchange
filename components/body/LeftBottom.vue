<template>
    <div class="LBContainer">
        <div class="dataTitle">
            <h2>My Position</h2>
            <div class="toggle">
                Show All Position
                <label class="switch">
                    <input type="checkbox" checked>
                    <span class="slider round"></span>
                </label>
            </div>
        </div>
        <div class="dataHeading">
            <div class="wrapper">
                <span>Market</span>
                <span>LONG / SHORT</span>
                <span>POSITION SIZE</span>
                <span>PNL</span>
                <span>Open notional</span>
                <span>Est. L. Price</span>
                <span>AVG. Open Price</span>
            </div>
        </div>
        <div class="data">
            <div class="dataWrapper">
                <div class="childWrapper">
                    <span>ETH - PERP</span>
                    <span>LONG</span>
                    <span>01 ETH</span>
                </div>
            </div>
            <div class="dataBtn">
                <button>Market close</button>
            </div>
        </div>
        <div class="data">
            <div class="dataWrapper">
                <div class="childWrapper">
                    <span>ETH - PERP</span>
                    <span>LONG</span>
                    <span>01 ETH</span>
                </div>
            </div>
            <div class="dataBtn">
                <button>Market close</button>
            </div>
        </div>
        <div class="data">
            <div class="dataWrapper">
                <div class="childWrapper">
                    <span>ETH - PERP</span>
                    <span>LONG</span>
                    <span>01 ETH</span>
                </div>
            </div>
            <div class="dataBtn dark">
                <button>Market close</button>
            </div>
        </div>
        <div class="data">
            <div class="dataWrapper">
                <div class="childWrapper">
                    <span>ETH - PERP</span>
                    <span>LONG</span>
                    <span>01 ETH</span>
                </div>
            </div>
            <div class="dataBtn dark">
                <button>Market close</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'LeftBottom'
    }
</script>

<style scoped>
.LBContainer{
    height: inherit;
    display: flex;
    flex-direction: column;
}
.dataTitle{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 12px 24px;
    border: 1px solid rgba(255, 255, 255, 0.13);
}
.dataTitle h2{
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    align-items: center;
    letter-spacing: 0.125em;
    text-transform: uppercase;
    color: #FFFFFF;
}
.toggle{
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 15px;
    color: #777E90;
}
.dataHeading{
    border: 1px solid rgba(255, 255, 255, 0.13);
    padding: 14px 24px 14px 24px;
}
.data{
    border: 1px solid rgba(255, 255, 255, 0.13);
    padding: 14px 24px 14px 24px;
    display: flex;
}
.wrapper{
    width: 85%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
.wrapper span{
    font-weight: 700;
    font-size: 11px;
    line-height: 17px;
    letter-spacing: -0.5px;
    text-transform: uppercase;
    color: #636D80;
}
.dataWrapper{
    width: 85%;
}
.childWrapper{
    width: 35%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
.childWrapper span:nth-child(1){
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 30px;
    color: #44DCFD;
}
.childWrapper span:nth-child(2){
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 30px;
    color: #00C600;
}
.childWrapper span:nth-child(3){
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 30px;
    color: #FFFFFF;
}
.dataBtn{
    width: 15%;
    display: flex;
    justify-content: flex-end;
}
button{
    border: 1px solid #F90101;
    border-radius: 6px;
    font-style: normal;
    font-weight: 500;
    font-size: 11px;
    line-height: 13px;
    text-align: center;
    text-transform: uppercase;
    color: #FFFFFF;
    padding: 4px 8px;
}
.dark button{
    background: linear-gradient(180deg, #FF0000 0%, #8F1100 100%);
}
/* toggle button */
.switch {
  position: relative;
  display: inline-block;
  width: 28px;
  height: 18px;
  margin-left: 8px;
}
.switch input { 
  opacity: 0;
  width: 0;
  height: 0;
}
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #23262F;
  -webkit-transition: .4s;
  transition: .4s;
}
.slider:before {
  position: absolute;
  content: "";
  height: 14px;
  width: 14px;
  left: 2px;
  top: 2px;
  background-color: #FF8663;
  -webkit-transition: .4s;
  transition: .4s;
}
input:checked + .slider {
  background-color: #516abc;
}

input:focus + .slider {
  box-shadow: 0 0 1px #516abc;
}

input:checked + .slider:before {
  -webkit-transform: translateX(10px);
  -ms-transform: translateX(10px);
  transform: translateX(10px);
}

.slider.round {
  border-radius: 10px;
}

.slider.round:before {
  border-radius: 50%;
}
/* toggle button */
</style>