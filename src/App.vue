<template> 
<div class="home-nav__match-wrapper home-nav__match-wrapper__app-download">
  <div class="container" style="overflow: visible;">
    <div class="display-flex-sb">
      <div class="display-flex-center">
        <div class="home-nav__icon-wrapper">
          <router-link to="/" class="nav-item nav-link ">
          <img src="/benner/logo.jpg" alt="Nature" class="responsive" width="40" style="border-radius: 50px;">
          </router-link>
        </div>
        <div class="home-nav__container">
           
          <router-link to="/livescore" class="home-nav__child relative">
              <div class="app-redirect">
                <div class="app-redirect__icon">
                  <div class="app-redirect__icon-bounce">
                    <img src="https://www.asiasport.com/img/loading.e3e10fab.gif" alt="">
                  </div>
                </div>
              </div>
              <span v-if="lang == 'en'">{{en.livescore}}</span>
              <span v-if="lang == 'kh'">{{kh.livescore}}</span>
              <div class="home-nav__child-indicator"></div>
          </router-link>
          <router-link to="/livestream" class="home-nav__child relative">
              <div class="app-redirect">
                <div class="app-redirect__icon">
                  <div class="app-redirect__icon-bounce">
                    <img src="/icon/—Pngtree—live icon vector_5587336.png" alt="">
                  </div>
                </div>
              </div>
              <span v-if="lang == 'en'">{{en.livestream}}</span>
              <span v-if="lang == 'kh'">{{kh.livestream}}</span>
              <div class="home-nav__child-indicator"></div>
          </router-link>

          <router-link to="/article" class="home-nav__child relative">
              <span v-if="lang == 'en'">{{en.article}}</span>
              <span v-if="lang == 'kh'">{{kh.article}}</span>
              <div class="home-nav__child-indicator"></div>
          </router-link>

          <router-link to="/highligh" class="home-nav__child relative">
              <span v-if="lang == 'en'">{{en.highligh}}</span>
              <span v-if="lang == 'kh'">{{kh.highligh}}</span>
              <div class="home-nav__child-indicator"></div>
          </router-link>
          
        </div>
    </div>
    <div class="display-flex-center">
      <div class="nav-pill__wrapper pb-0" hidden>
        <a href="/kh/signin" class="nav-pill">ចុះឈ្មោះចូល</a>
        <a href="/kh/signup" class="nav-pill">ចុះឈ្មោះ</a>
      </div>

  <div class="language-wrapper"  @mouseover="hover = true"
        @mouseleave="hover = false">
    <div class="langauge-selection__wrapper">

      <div class="langauge-selection">
        <img class="img-contain" :src="'/icon/'+ this.lang+'.png'">
      </div>
    </div>
      <div class="language-list__wrapper" :class="{ selected: hover }">
        <div class="language-list__container" @click="goToGame('en')">
          <div class="language-list__name">
            <img class="img-contain language-list__name-icon" src="/icon/en.png">
            <span>English</span> 
            <span><img src="/icon/active.png" alt="" v-if="lang == 'en'"></span> 
          </div>
          <div class="language-list__tick"></div>
        </div>
        <div class="language-list__container" @click="goToGame('kh')">
          <div class="language-list__name">
            <img class="img-contain language-list__name-icon" src="/icon/kh.png"> 
            <span>ភាសាខ្មែរ</span> 
            <span><img src="/icon/active.png" alt="" v-if="lang == 'kh'"></span> 

          </div>
          <div class="language-list__tick selected"></div>
        </div>
      </div>
  </div>
</div>
</div>
</div>
  <div class="container" style="overflow: visible;">
      <div class="display-flex-sb">
        <div class="home-nav__container8">
           
           <router-link to="/livescore" class="home-nav__child relative">
               <div class="app-redirect">
                 <div class="app-redirect__icon">
                   <div class="app-redirect__icon-bounce">
                     <img src="https://www.asiasport.com/img/loading.e3e10fab.gif" alt="">
                   </div>
                 </div>
               </div>
               <span v-if="lang == 'en'">{{en.livescore}}</span>
               <span v-if="lang == 'kh'">{{kh.livescore}}</span>
               <div class="home-nav__child-indicator"></div>
           </router-link>
           <router-link to="/livestream" class="home-nav__child relative">
               <span v-if="lang == 'en'">{{en.livestream}}</span>
               <span v-if="lang == 'kh'">{{kh.livestream}}</span>
               <div class="home-nav__child-indicator"></div>
           </router-link>
 
           <router-link to="/article" class="home-nav__child relative">
               <span v-if="lang == 'en'">{{en.article}}</span>
               <span v-if="lang == 'kh'">{{kh.article}}</span>
               <div class="home-nav__child-indicator"></div>
           </router-link>
 
           <router-link to="/highligh" class="home-nav__child relative">
               <span v-if="lang == 'en'">{{en.highligh}}</span>
               <span v-if="lang == 'kh'">{{kh.highligh}}</span>
               <div class="home-nav__child-indicator"></div>
           </router-link>
           
</div>
    </div>
  </div>
</div>
  <router-view/>
  <div class="bg-blue-900 mt-2">
    <div class="mx-auto flex flex-col items-center justify-center bg-fan-primary">
      <div class="flex flex-col py-3 gap-y-5 md:py-3 lg:py-3 md:flex-row lg:flex-row items-center md:gap-x-10 lg:gap-x-10">
        <ul class="nav-footer-text nav-footer justify-content-end"  v-for="(value, key, index) in  footer " :key="index">
          <li class="nav-item">
            <a :href="'https://www.'+value.link" rel="noopener" class="nav-link text-white">
                <img :src="'https://share-sport.2m-sport.com/banner/'+value.photo" alt="" style="width: 25px;">
            </a>
          </li>
        </ul>
        <ul class="nav-footer-text nav-footer justify-content-end">
          <li class="nav-item">
            <a class="nav-link text-white text-buttom" v-if="lang == 'en'">
              ©{{year}} {{en.copyright}}
            </a>
            <a class="nav-link text-white text-buttom" v-if="lang == 'kh'">
              ©{{year}} {{kh.copyright}}
            </a>
          </li>
        </ul>
      
      </div>
    </div>
  </div>
  <div v-if="showModal == true" >
        <div class="h-full w-full fixed top-0 left-0 z-20"></div>
        <div class="bg-fan-sila radis-sila rounded-lg text-lg pt-6 shadow-lg w-96 fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-30">
            <div class="px-6 pb-6 text-center ">
                <div class="text-gray-600 font-light text-white" style="margin: 10px;"  v-if="lang == 'en'">{{ en.you_can_change_language }}</div>
                <div class="text-gray-600 font-light text-white" style="margin: 10px;" v-if="lang == 'kh'">{{ kh.you_can_change_language }}</div>
            </div>
            <ul class="cursor-pointer border-t border-gray-100" >
                <li @click="goToGame('kh')" class="border-b text-blue-500 border-gray-100 w-full px-6 py-3 hover:bg-gray-100" 
                style="border-top: 1px solid white;">
                  <button>
                    <a >
                      <div>
                        <div class="flex items-center gap-x-2 px-7">
                          <img src="/icon/kh.png" alt="">
                          <span class="inline-block lg:text-lg md:text-lg text-lg font-medium text-white"> ភាសាខ្មែរ</span>
                          <img src="/icon/active.png" alt="" v-if="lang == 'kh'">
                        </div>
                      </div>
                    </a>
                  </button>
                </li>
                <li @click="goToGame('en')" class="border-b text-blue-500 border-gray-100 w-full px-6 py-3 hover:bg-gray-100">
                  <button>
                    <a >
                      <div>
                        <div class="flex items-center gap-x-2 px-7">
                          <img src="/icon/en.png" alt="">
                          <span class="inline-block lg:text-lg md:text-lg text-lg font-medium text-back text-white">English</span>
                          <img src="/icon/active.png" alt="" v-if="lang == 'en'">
                        </div>
                      </div>
                    </a>
                  </button>
                </li>
            </ul>
        </div>
  </div>

</template>
<script>
      // import router from "./router";
    const axios = require("axios");
    import en from "./en.js";
      import kh from "./kh.js";
      if (localStorage.lang) {
        localStorage.lang;
      }
      else{
        localStorage.lang ='kh';
      }
      const current = new Date();
    export default {
      mixins:[en,kh],
      data() {
        return { 
          lang: localStorage.lang,
          show: false,
          showModal:false,
          year:`${current.getFullYear()}`,
          footer:[],
          hover: false,
        }
      },
      computed:{
        routePath(){
          return this.$route.path 
        },
        routeName(){
          return this.$route.name
        },
        
      },
      mounted(){
        this.getfooter();
      },
      methods: {
        reloadPage() {
          window.location.reload();
        },
        goToGame(text){
          this.hover = false,
          localStorage.lang = text;
          this.lang = text;
          this.showModal = false
          this.reloadPage();
        },
        display() {
          console.log("clicked")
          this.show = !this.show
        },
        popup_lang(){
          this.showModal = true
          console.log('sila');
        },
        //=====footer=========
        getfooter(){
          axios.get("https://share-sport.2m-sport.com/api/footer").then((res)=>{
              this.footer = res.data;
          }).catch(function (error) {
              console.error(error);
          });
          },
        //=====the-end=========
      }
    }

</script>

<style scoped>
  .home-nav__container8{
    display: none;
  }
@media (max-width: 800px) {
  .home-nav__container{
    display: none !important;
  }
  .home-nav__container8{
    padding-top: 10px;
    display: flex !important;
    margin-left:10% ;
  }
}
.home-nav__child:hover .home-nav__child-indicator {
    width: 80%;
    height: 0.2rem;
    background-color: #ffde4a;
    border-radius: 1rem;
    margin-top: 0.3rem;
    text-align: center;
    margin: 0 auto;
    margin-top: 0.2rem;
    display: block!important;
}
a.router-link-exact-active {
    color: #ffde4a;
}
.home-nav__child span{
  text-transform: uppercase !important;
}
.home-nav__child:hover span {
    font-weight: 700;
    color: #ffde4a;
}
.nav-pill:hover{
  background-color: #2f2151;
  color: #fff;
}
.language-list__wrapper .language-list__container:hover{
  background: #453176a8 !important;
  border-radius: 5px;
}
.home-nav__match-wrapper {
    position: relative;
    z-index: 3;
    padding: 1.5rem 0;
    background: #6f4b98;
}
.display-flex-sb {
    align-items: center;
    justify-content: space-between;
}

.display-flex, .display-flex-align-baseline, .display-flex-align-center, .display-flex-align-end, .display-flex-align-start, .display-flex-center, .display-flex-fe, .display-flex-fs, .display-flex-justify-center, .display-flex-sa, .display-flex-sb, .display-flex-sb-t, .display-flex-se {
    display: flex;
}
.app-redirect__icon-bounce{
    width: 3.125rem;
    position: absolute;
    top: -2rem;
    left: -0.5rem;
}
.display-flex-center {
    align-items: center;
    justify-content: center;
}
.pb-0 {
    padding-bottom: 0;
}
.nav-pill__wrapper {
    display: flex;
    align-items: center;
    padding-bottom: 1rem;
    white-space: nowrap;
}
.language-wrapper{
    position: relative;
}
.langauge-selection__wrapper{
    width: 3.5rem;
    display: flex;
    justify-content: flex-end;
}
.img-contain {
    -o-object-fit: contain;
    object-fit: contain;
}
.langauge-selection,.mobile-default-avatar-wrapper {
    position: relative;
    width: 1.8rem;
    height: 1.8rem;
    border-radius: 50%;
    padding: 0.3rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--color-grey-60);
    cursor: pointer;
}
.language-list__name span{
    color: white;
}
.language-list__wrapper{
    position: absolute;
    top: 100%;
    right: 0;
    margin-top: 0.1rem;
    min-width: 12rem;
    background-color: #2f2151;
    padding: 0.5rem 0.3rem;
    border-radius: 0.5rem;
    transform: scale(0);
    transform-origin: 11.5rem 0;
    transition: all .3s;
}
.language-list__container{
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.3rem 0.5rem;
    cursor: pointer;
    transition: all .3s;
}
.language-list__tick{
    width: 1rem;
    height: 1rem;
}
.language-list__name{
    display: flex;
    align-items: center;
    font-size: .88rem;
}
.language-list__name-icon{
    -o-object-fit: contain;
    object-fit: contain;
    margin-right: 0.7rem;
    width: 1.5rem;
    height: 1.5rem;
}
.app-redirect{
    font-size: .625rem;
    line-height: .875rem;
    font-weight: 700;
    margin-right: 0.75rem;
    display: flex;
    align-items: center;
    position: relative;
}
.app-redirect img{
    width: 100%;
    height: 100%;
    -o-object-fit: contain;
    object-fit: contain;
}
.app-redirect__icon{
    width: 2.375rem;
}
.nav-pill {
    border: 0.1rem solid #fff;
    border-radius: 1rem;
    color: #fff;
    padding: 0.25rem 0.7rem;
    margin-right: 0.5rem;
    font-size: .8rem;
    cursor: pointer;
    position: relative;
    white-space: nowrap;
    background-color: transparent;
}
.nav-pill.selected {
    background-color: var(--bg-selected)!important;
    color: #000!important;
    border: 0.1rem solid var(--bg-selected)!important;
    font-weight: 700!important;
}
.home-nav__icon-wrapper {
    margin-right: 2rem;
    padding: 0.2rem;
    border-radius: 0.5rem;
}
.home-logo {
    width: 5rem;
}
.home-nav__container {
    display: flex;
}
.home-nav__child.selected {
    font-weight: 700!important;
}

.home-nav__child {
    color: #fff;
    margin-right: 1rem;
    transition: all .3s;
    font-size: .88rem;
    cursor: pointer;
    transition: all .25s;
}
.router-link-exact-active span {
    font-weight: 700;
}
.router-link-exact-active .home-nav__child-indicator {
    width: 80%;
    height: 0.2rem;
    background-color: #ffde4a;
    border-radius: 1rem;
    margin-top: 0.3rem;
    text-align: center;
    margin: 0 auto;
    margin-top: 0.2rem;
    display: block!important;
}

.selected .home-nav__child-indicator {
    display: block!important;
}
.home-nav__child {
    color: #fff;
    margin-right: 1rem;
    transition: all .3s;
    font-size: .88rem;
    cursor: pointer;
    transition: all .25s;
}
.relative {
    position: relative;
}
.langauge-selection, .mobile-default-avatar-wrapper {
    position: relative;
    width: 1.8rem;
    height: 1.8rem;
    border-radius: 50%;
    padding: 0.3rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #2e2151;
    cursor: pointer;
}
.language-list__wrapper.selected{
    transform: scale(1);
}



  #nav a{
    border-bottom: 5px solid #6f4b98;
    border-radius: 5px;
  }
  #nav a:hover{
    border-bottom: 5px solid yellow;
    border-radius: 5px;
  }
.bg-fan-sila ul li:hover{
  background-color: #41316c;
}
.yearlo{
  color: rgb(255, 222, 74);
}
.bg-fan-sila{
  background-color: #2e2151;
}
dl, ol, ul {
    margin-bottom: 0px !important;
}
.text-black{
  color: black;
}
.transform ul {
    padding-left: unset !important;
}
.bounce-enter-active {
    animation: bounce-in .5s ease-out both;
}

.bounce-leave-active {
    animation: bounce-in .5s reverse ease-in both;
}

@keyframes bounce-in {
    0% {
        transform: scale(0);
    }
    50% {
        transform: scale(1.10);
    }
    100% {
        transform: scale(1);
    }
}
@media (max-width: 999px) {
  .change_lang{
    display: none
    ;
  }
  .change_lang_min{
    display: block;
  }

}

.dropbtn {
  background-color:white;
  color: #2e2151;
  padding: 5px;
  font-size: 16px;
  border: none;
  border-radius: 50px;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #2e2151;
  /* margin-right: 180px; */
  min-width: 150px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  border-radius: 5px;
  overflow: hidden;
}

.dropdown-content a {
  color: white;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  
}

.dropdown-content a:hover {
  background-color: #262230;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #2e2151;
  border-radius: 50px;
  color: white;

}






  .flexby .form-control {
    border-radius: 10px !important;
  }
  .search-icon{
    padding-bottom: 10px;
  }
  .search-type{
    display: none;
  }
  .example {
    display: none;
  }
  .box-highligh::-webkit-scrollbar {
    display: none;
  }
  @media (max-width: 999px) {
    .search-btn{
      height: 32px;
      padding-bottom: 10px;
    }
    .search-type .btn {
    /* background-color:rgb(255, 222, 74); */
    border-radius: 0px;color: white;
    border-bottom-right-radius: 10px;
    border-top-right-radius: 10px;
  }
  input:focus {
    border-color: inherit;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
    .search-icon{
      padding-bottom: 8px;
    }
    .search-type{
      display: block;
    }
    .nav-link-example {
        padding-right: var(--bs-navbar-nav-link-padding-x);
        padding-left: var(--bs-navbar-nav-link-padding-x);
    }

    .new-mumu{
      display: block;
    }
    .example {
      width: 400px;
      overflow-x: scroll;
      padding: 10px;
    }

  .example::-webkit-scrollbar {
      display: none;
  }

  .example {
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
    white-space: nowrap;
  }
}
.nav-link{
margin: 5px;
}

.nav-footer{
  text-align: center;
}
li a{
  color: white !important;
}
.justify-content-end {
    -webkit-box-pack: end !important;
    -ms-flex-pack: end !important;
    justify-content: flex-end !important;
}
.nav-footer-text {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    padding-left: 0;
    list-style: none;
    align-items: center;
}
ol, ul, dl {
    margin-top: 0;
    margin-bottom: 1rem;
}
  .secondary {
      background-color: #2e2151 !important;
      border-color: #2e2151 !important;
  }
  div a {
      color: black;
      text-decoration: auto;
  } 
  .from-blue-900 {
      --tw-gradient-from: #2f2151;
      --tw-gradient-stops: var(--tw-gradient-from), var(--tw-gradient-to, rgba(30, 58, 138, 0));
  }
  .bg-blue-900 {
      --tw-bg-opacity: 1;
      background-color: rgba(30, 58, 138, var(--tw-bg-opacity));
  }

  .mt-2 {
      margin-top: 0.5rem;
  }
  .bg-blue-900 {
      --tw-bg-opacity: 1;
      background-color: rgba(30, 58, 138, var(--tw-bg-opacity));
  }
  .mt-2 {
      margin-top: 0.5rem;
  }
  .justify-center {
      justify-content: center;
  }

  .items-center {
      align-items: center;
  }
  @media (max-width: 1000px) {
        .flexby .search {
            display: none;
          }
          .flexby .btn {
            display: none;
          }
    }
  @import url('https://fonts.googleapis.com/css2?family=Hanuman&display=swap');
  #nav a:hover{
    color:rgb(255, 222, 74);
    /* border-bottom: 2px solid; */
    }
  .flexby{
    background-color:white;
    border-radius: 10px;
    max-height: 30px;
    max-width: 220px;
  }
  .flexby .btn {
    /* background-color:rgb(255, 222, 74); */
    /* border-radius: 0px;color: white; */
    border-bottom-right-radius: 10px;
    border-top-right-radius: 10px;
  }
  .form-control:focus {
    border-color: inherit;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
  .responsive {
    max-width: 100%;
    height: auto;
  }
  #nav a {
    color: white;
    font-size: 17px;
  }

  #nav a.router-link-exact-active {
    color:rgb(255, 222, 74);
  }
  #nav a.router-link-exact-active {
    color:rgb(255, 222, 74);
  }
  .bg-fan-primary {
      background-color: #6f4b98;
  }

</style>

