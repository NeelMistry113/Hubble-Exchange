<template>
  <div>
    <header>
      <navbar/>
    </header>
    <main>
      <homepage/>
    </main>
    <footer>
      <page-footer/>
    </footer>
  </div>
</template>

<script>
import Homepage from '~/components/body/Homepage.vue'
import PageFooter from '~/components/footer/PageFooter.vue'
import Navbar from '~/components/header/Navbar.vue'
export default {
  components: { Navbar, Homepage, PageFooter },
  name: 'IndexPage',
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&family=Open+Sans:wght@400;500;600;700&display=swap');

*{
  margin: 0;
  padding: 0;
  /* background: #141416; */
  background:transparent;
  font-family: 'Inter', sans-serif;
  color: #fff;
  color: inherit;
}
body::-webkit-scrollbar{
  display: none;
}
main{
  display: flex;
  flex-direction: column;
}
</style>