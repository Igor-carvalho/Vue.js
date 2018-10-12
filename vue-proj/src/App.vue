<template>
<div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <!-- <Skills /> -->
    <nav>
        <router-link :to="{name:'skills'}">Home</router-link>
        <router-link to='about'>About</router-link>
        <router-link to='/about'>About</router-link>
    </nav>
    <router-view></router-view>
</div>
</template>

<script>
import Skills from './components/Skills.vue'
// import MarkdownEditor from './components/MarkdownEditor'

export default {
    name: 'app',
    components: {
        Skills,
    }
}
</script>

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 10px;
    width: 50%;
}

@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');

body {
    background-color: #EEEEEE;
    font-family: 'Montserrat', sans-serif;
    display: grid;
    grid-template-rows: auto;
    justify-items: center;
    padding-top: 50px;
}

nav {
    padding: 20px 20px 20px 0;
}

nav a {
    padding: 10px;
    text-decoration: none;
    background: #fff;
    border-radius: 3px;
    color: rgb(0, 110, 255);
    font-weight: bold;
    margin-right: 15px;
}

body,
html {
    margin: 0;
    height: 100%;
}
</style>
