<template>
    <div class="container">
        <div class="upperContainer">
            <div class="leftUpper">
                <left-upper/>
            </div>
            <div class="rightUpper">
                <right-upper/>
            </div>
        </div>
        <div class="midContainer">
            <div class="leftMid">
                <left-mid/>
            </div>
            <div class="midMid"></div>
            <div class="rightMid">
                <right-mid/>
            </div>
        </div>
        <div class="bottomContainer">
            <div class="leftBottom">
                <left-bottom/>
            </div>
            <div class="rightBottom">
                <right-bottom/>
            </div>
        </div>
    </div>
</template>

<script>
import LeftBottom from './LeftBottom.vue'
import LeftMid from './LeftMid.vue'
import LeftUpper from './LeftUpper.vue'
import RightBottom from './RightBottom.vue'
import RightMid from './RightMid.vue'
import RightUpper from './RightUpper.vue'
    export default {
  components: { RightUpper, RightBottom, LeftMid, LeftUpper, LeftBottom, RightMid },
        name: 'Homepage'
    }
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: column;
    /* overflow: hidden; */
     background: #141416;
     color: #fff;
}

/* Upper-Container */
.upperContainer{
    display: flex;
    flex-direction: row;
    height: 80px;
}

.leftUpper{
    width: 75vw;
    height: 100%;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #ADDC7B , #4E603D, #23262F 99%);
    border-image-slice: 1;
}
.rightUpper{
    width: 25vw;
    height: 100%;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #259DA8 , #259DA8, #23262F 99%);
    border-image-slice: 1;
}

/* Mid-Container */
.midContainer{
    display: flex;
    flex-direction: row;
    height: 600px;
}

.leftMid{
    width: 25vw;
    height: 100%;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #E5CF00 , #E6CF01, #23262F 99%);
    border-image-slice: 1;
}
.midMid{
    width: 50vw;
    height: 100%;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #05FF00 , #05FF01, #23262F 99%);
    border-image-slice: 1;
}
.rightMid{
    width: 25vw;
    height: 100%;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom right, #32C5FF , #B620E0, #FFAA12 99%);
    border-image-slice: 1;
}

/* Bottom-Container */
.bottomContainer{
    display: flex;
    flex-direction: row;
    height: auto;
}
.leftBottom{
    width: 75vw;
    height: 336px;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #FF8663 , #FF8663, #23262F 99%);
    border-image-slice: 1;
}
.rightBottom{
    width: 25vw;
    height: 336px;
    border: 1px solid transparent;
    border-image: linear-gradient(to bottom, #F8BD3F , #CD9725, #23262F 99%);
    border-image-slice: 1;
}
</style>