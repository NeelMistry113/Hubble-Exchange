<template>
    <div class="container">
        <div class="footData">
            <p>© 2021 Hubble Exchange All Rights Reserved</p>
            <a href="">Whitepaper</a>
            <a href="">Contact us</a>
            <a href="">Join Community</a>
        </div>
        <button hred="#">Share Feedback</button>
    </div>
</template>

<script>
    export default {
        name: 'PageFooter'
    }
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    height: 86px;
    padding-left: 38px;
    padding-right: 38px;
    background: #141416;
    color: #fff;
    /* border: 1px solid red; */
}
.footData{
    display: flex;
    font-size: 14px;
    line-height: 17px;
    text-align: center;  
    color: #777E90;
}

.footData a {
    text-decoration: none;
    margin-left: 30px;
    color: #777E90;
}

.footData a:hover{
    color: rgba(89, 89, 202, 0.619);
}
.footData p{
    color: #777E90;
}

button{
    padding: 8px 22px;
    background: linear-gradient(210.04deg, #FFAC5F -24.31%, #B94BBE 50.53%, #F161F7 115.86%);
    border-radius: 90px;
    cursor: pointer;
}
</style>