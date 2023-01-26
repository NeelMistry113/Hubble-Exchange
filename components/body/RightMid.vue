<template>
    <div class="RMContainer">
        <div class="heading">
            <div class="buttons">
                <span>BUY</span>
                <span>SELL</span>
            </div>
            <img src="../../asset/Setting.png" alt="">
        </div>
        <div class="wrapper">
            <div class="dataWrapp1">
                <div class="input">
                    <span>ETH</span>
                    <div class="inputWrapper">
                        <input type="number" placeholder="0" name="input-one" id="input-one" v-model="amountOne" @input="fetchData()" />
                        <span>ETH</span>
                    </div>
                </div>
                <div class="input secondInput">
                    <span>USD</span>
                    <div class="inputWrapper">
                        <input type="number" placeholder="0" name="input-two" id="input-two" v-model="amountTwo" @input="fetchData2()"/>
                        <span>USD</span>
                    </div>
                </div>
            </div>
            <div class="leverage">
                <h3>Set Leverage</h3>
                <div class="leverageWrappe">
                    <input type="range" class="slider" min="0" max="100" v-model="value">
                    <span class="rangeValue"> {{ value }} %</span>
                </div>
            </div>
            <div class="wrapperbuttons">
                <div class="wbtn1">
                    <div class="wbtnq">
                        <span class="textSpan">Account Leverage</span>
                        <img src="../../asset/help-circle.png" alt="" width="12px" height="12px">
                    </div>
                    <span class="textSpan">0</span>
                </div>
                <div class="wbtn1 secondwbtn1">
                    <div class="wbtnq">
                        <span class="textSpan">Estimated Liqidation Price</span>
                        <img src="../../asset/help-circle.png" alt="" width="12px" height="12px">
                    </div>
                    <span class="textSpan">0</span>
                </div>
                <div class="btn">BUY</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'RightMid',
        data() {
            return {
            data:[],
            currency_one:"USD",
            currency_two:"INR",
            rate:"",
            amountOne:1,
            amountTwo: 0,
            value: "10",
            };
        },

        methods: {
            fetchData(){
            fetch(`https://v6.exchangerate-api.com/v6/32c351b19021ab68237a8e33/latest/${this.currency_one}`
            )
            .then((res)=> res.json())
            .then((data) => {
                console.log(data)
                this.data = data;
                this.rate = data.conversion_rates[this.currency_two];
                this.amountTwo = this.amountOne * this.rate.toFixed(2)
            });
            },

            fetchData2(){
            fetch(`https://v6.exchangerate-api.com/v6/32c351b19021ab68237a8e33/latest/${this.currency_two}`
            )
            .then((res)=> res.json())
            .then((data) => { 
                console.log(data)
                this.data = data;
                this.rate = data.conversion_rates[this.currency_one];
                this.amountOne = this.amountTwo * this.rate.toFixed(2)
            });
            },

            switchValue(){
            const temporaryValue = this.currency_one 
            this.currency_one = this.currency_two
            this.currency_two = temporaryValue
            this.fetchData();
            }
        },

        mounted(){
            this.fetchData();
        }
    }
</script>

<style scoped>
.RMContainer{
    height: inherit;
    display: flex;
    flex-direction: column;
}
.heading{
    border: 1px solid #353945;
    padding: 12px 24px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
.heading img{
    cursor: pointer;
}
.buttons span:nth-child(1){
    font-size: 16px;
    line-height: 19px;
    color: #56C200;
    cursor: pointer;
}
.buttons span:nth-child(2){
    font-size: 16px;
    line-height: 19px;
    color: #777E90;
    margin-left: 14px;
    cursor: pointer;
}
.wrapper{
    padding: 20px 24px; 
    height: inherit;
    display: flex;
    flex-direction:column;
    justify-content: space-between;
}
.dataWrapp1{
    display: flex;
    flex-direction: column;
}
.inputWrapper{
    display: flex;
    align-items: center;
    height: 54px;
    padding-left: 24px;
    padding-right: 24px;
    border: 2px solid #23262F;
    border-radius: 12px;
    margin-top: 16px;
}
.inputWrapper span{
    font-weight: 600;
    font-size: 14px;
    line-height: 24px;
    text-align: right;
    color: #777E91;
}
.input{
    display: flex;
    flex-direction: column;
    font-size: 14px;
    line-height: 17px;
    color: #FFFFFF;
}
input{
    width: 100%;
    height: 100%;
    outline: none;
    -webkit-appearance: none;
    -ms-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border: none;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
.secondInput{
    margin-top: 26px;
}

.leverage{
    display: flex;
    flex-direction: column;
}
.leverage h3{
    font-weight: 600;
    font-size: 14px;
    line-height: 17px;
    text-transform: uppercase;
    color: #FFFFFF;
}

.leverageWrappe{
    display: flex;
    flex-direction: row;
    align-items: flex-end;
}
.rangeValue{
    width: 66px;
    height: 43px;
    font-weight: 600;
    font-size: 14px;
    line-height: 24px;
    color: #FFFFFF;
    text-align: right;
    border: 2px solid #23262F;
    border-radius: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 18px;
}
.slider{
    height: 4px;
    margin-bottom: 6px;
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    border-radius: 100px;
    background: linear-gradient(222.94deg, rgba(50, 197, 255, 0.65) 0%, #B620E0 45.93%, rgba(255, 170, 18, 0.27) 86.01%);
}

.slider::-webkit-slider-thumb{
    -webkit-appearance: none;
    appearance: none;
    width: 32px;
    height: 20px;
    background: #FFFFFF;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
    border-radius: 4px;
    cursor: pointer;
}

.slider::-moz-range-thumb{
    -moz-appearance: none;
    appearance: none;
    width: 32px;
    height: 20px;
    background: #FFFFFF;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
    border-radius: 4px;
    cursor: pointer;
}

.wrapperbuttons{
    
}
.wbtn1{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    color: #777E90;
    border: 2px solid #23262F;
    border-radius: 12px;
    padding: 12px 18px; 
    cursor:help;
}
.wbtnq {
    display: flex;
    flex-direction: row;
    align-items: center;
}
.wbtnq img{
    margin-left: 8px;
}
.textSpan{
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    color: #777E90;
}
.secondwbtn1{
    margin-top: 18px;
}
.btn{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 60px;
    background: linear-gradient(222.94deg, #32C5FF 0%, #B620E0 45.93%, #FFAA12 86.01%);
    border-radius: 12px;
    margin-top: 18px;
    cursor: pointer;
}
</style>