<template>
    <div class="navContainer">
        <div class="menu-item active"><NuxtLink to="/" active-class="menu-item active">Home</NuxtLink></div>
        <div class="menu-item"><NuxtLink to="/error" active-class="menu-item active">Balance </NuxtLink></div>
        <div class="menu-item"><NuxtLink to="/error" active-class="menu-item active">Positions</NuxtLink></div>
        <div class="menu-item"><NuxtLink to="/error" active-class="menu-item active">Funding Payment</NuxtLink></div>
        <div class="menu-item"><NuxtLink to="/error" active-class="menu-item active">Maker</NuxtLink></div>
    </div>
</template>

<script>
    export default {
        name: 'Navlinks'
    }
</script>

<style scoped>
.navContainer{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
}

.menu-item {
    margin-right: 8px;
    margin-left: 8px;
    font-size: 14px;
}
.menu-item a.active,
.menu-item a:hover{
    background: linear-gradient(222.94deg, #32C5FF 0%, #B620E0 45.93%, #FFAA12 86.01%);
    color: #fff;
}
.menu-item a {
    text-decoration: none;
    background: transparent ;
    padding: 6px 14px;
    border-radius: 53px;
    color: #777E90;
}
</style>