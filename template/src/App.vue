<template>
  <div id="app">
    <Nav/>
    {{#router}}
    <router-view/>
    {{else}}
    <Home/>
    {{/router}}
  </div>
</template>

<script>
import Nav from './components/Nav';
{{#unless router}}
import Home from './components/Home'

{{/unless}}
export default {
  name: 'App',
  components: {
    Nav,
    {{#router}}{{else}}
    Home
    {{/router}}
  }
}
</script>

{{#bootstrap}}
<style lang='scss'>
@import '~@/styles/custom-bootstrap';
{{else}}
<style>
{{/bootstrap}}
</style>
