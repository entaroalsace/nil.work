<template>
  <div id="app">
    <router-link id="logo" to="/">
      <h1>NIL</h1>
      <h1>WO</h1>
      <h1>RK</h1>
    </router-link>
    <back-btn class="backBtn" :class="{hideIndicator:activeProj == null,scrollIsAnimating:isAnimating}">
      <i class="material-icons">keyboard_backspace</i>
    </back-btn>
    <about :class="{hideAbout: !isAboutPage}"></about>
    <scroller class="scroller" :class="{slideDown:isAboutPage,scrollIsAnimating:isAnimating}" :projects="projects" :activeProj="activeProj"></scroller>
    <scroller-indicator class="scrollIndicator" :class="{slideDown:isAboutPage,scrollIsAnimating:isAnimating}" :projects="projects"></scroller-indicator>
    <side-nav class="sideNav"></side-nav>
    <router-view></router-view>
  </div>
</template>

<script src="./App.js"></script>

<style lang="scss">
  @import 'styles.scss';
  @import 'fonts.scss';
  #logo{top:32px;left:32px;position:fixed;z-index: 10;}
  #logo h1{font:800 28px/32px Raleway;margin:0}
  .slideDown{transform: translateY(120%);top: 120% !important;}
  /*.fade{opacity: 0;transform: scale(1.07)}*/
  .scrollIsAnimating{transition: 0.5s ease-in-out !important;}
  .hideAbout{top:-120% !important;}
  .hideIndicator{opacity: 0;pointer-events: none;}
  @media (max-width:600px){
    #logo{left:24px;top:24px;} #logo h1{font-size:24px;line-height: 28px;}
    .scrollIndicator{display:none;}
    .sideNav{left:24px;right:auto !important;}
    .scroller{left:24px !important;}
    .backBtn{left:24px !important;}
  }
</style>
