<template>
    <div @click="isOpen = !isOpen">
        <div class="img" v-if="!isOpen">
            <a href=""></a>
            <img src="../../asset/Dropdown.png" alt="">
        </div>

        <div class="img2" v-if="isOpen">
            <a href=""></a>
            <img src="../../asset/DropClose.png" alt="">
        </div>

        <transition name="fade" appear>
        <div class="sub-menu" v-if="isOpen">
            <a class="link" href="">
                <img src="../../asset/1.png" alt="">
                Read Draftpaper 
            </a>
            <a class="link" href="">
                <img src="../../asset/2.png" alt="">
                Follow on Twitter 
            </a>
            <a class="link" href="">
                <img src="../../asset/3.png" alt="">
                Join us on Discord 
            </a>
            <a class="link" href="">
                <img src="../../asset/4.png" alt="">
                Telegram Community
            </a>
            <a class="link" href="">
                <img src="../../asset/5.png" alt="">
                Submit Feedback
            </a>
            <a class="link" href="">
                <img src="../../asset/6.png" alt="">
                Feature Request
            </a>
            <a class="link" href="">
                <img src="../../asset/7.png" alt="">
                Contact us
            </a>
            <a class="link lastlink" href="">
                <img src="../../asset/8.png" alt="">
                Medium 
            </a>
        </div>
        </transition>
    </div>  
</template>

<script>
    export default {
        name: 'DropComp',
        data() {
            return {
               isOpen: false
            }
        }
    }
</script>

<style scoped>
.img{
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    /* border: 1px solid red; */
}
.img2{
    margin-top: 8px;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    /* border: 1px solid red; */
}
.sub-menu{
    position: absolute;
    top: 88px;
    right: 24px;
    background: #23262F;
    box-shadow: 0px 16px 64px -48px rgba(31, 47, 70, 0.15);
    border-radius: 12px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    width: auto;
    overflow: hidden;
}

.fade-enter-active,
.fade-leave-active {
  transition: all .3s ease-in-out;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.link {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    text-decoration: none;
    text-align: center;
    color: #E3E3E3;
    font-style: normal;
    font-size: 14px;
    line-height: 17px;
    width: 258px;
    height: 70px;
    background: #23262F;
    border-bottom: 1px solid #353945;
    padding-left: 18px;
}
.link:hover{
    background: #1B1B1F;
}
.lastlink {
    border-bottom: none;
}
.link img{
    margin-right: 14px;
    background: transparent;
}
</style>