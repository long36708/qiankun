<template>
  <div id="app">
    <div id="nav">
<!--      <RemoteComp name="在 codesandbox 中加载" />-->
      <LazyLoadComp/>
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>
<script>
import comps from "hel-tpl-remote-vue2-rsbuild-comp";
import { preFetchLib } from 'hel-micro';

export default {
  name: 'app',
  components:{
    RemoteComp: comps.App,
    // RemoteComp: async () => {
    //       const mod = await preFetchLib("hel-tpl-remote-vue2-rsbuild-comp",{
    //         custom: {
    //           host: 'http://localhost:7001', // 微模块开发环境联调
    //           // host: 'http://localhost:9001', // 微模块打包后联调
    //           enable: true,
    //         },
    //       });
    //   // const mod = await preFetchLib("remote-selection-point", "0.0.1-alpha.3");
    //   // const mod = await preFetchLib("hel-tpl-remote-vue-comps");
    //   return mod.App;
    // },
    // LazyLoadComp:  () =>  comps.LazyLoadComp(),
    // LazyLoadComp:  () => ({
    //   component: new Promise(async (r, j) => {
    //     try {
    //       const mod = await preFetchLib("hel-tpl-remote-vue2-rsbuild-comp",{
    //         custom: {
    //           host: 'http://localhost:7001', // 微模块开发环境联调
    //           // host: 'http://localhost:9001', // 微模块打包后联调
    //           enable: true,
    //         },
    //       });
    //       r(mod.LazyLoadComp);
    //     } catch (err) {
    //       j(err);
    //     }
    //   }),
    //
    //   // 可能因为编译器的关系，此写法无效
    //   // component: async () => {
    //   //   const mod = await preFetchLib("hel-tpl-remote-vue2-rsbuild-comp");
    //   //   console.log("---> mod", mod);
    //   //   return mod.LazyLoadComp();
    //   // },
    //   // component: import("./Async"),
    //   // loading: Loading,
    //   // error: Loading,
    //   delay: 1,
    //   timeout: 3000,
    // }),
  }
};
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding-bottom: 20px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
