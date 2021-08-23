<template>
  <div id="app">
    <Navbar />
    <Cards />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
import Cards from '@/components/Cards'

export default {
  name: 'App',
  components: {
    Navbar,
    Cards
  }
}
</script>
