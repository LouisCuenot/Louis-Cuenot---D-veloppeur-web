<template>
  <div v-on:mousemove="curs">
    <router-link to="/" id="logo">
          <svg  xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 200" id="svg" fill="#ff4655">
            
              <rect y="181.72" width="200" height="18.28" />
              <rect x="100" y="81.72" width="181.72" height="18.28" transform="translate(100 281.72) rotate(-90)" />
              <rect x="-68.01" y="68.01" width="154.3" height="18.28" transform="translate(-68.01 86.29) rotate(-90)" />
              <rect x="18.28" width="73.12" height="18.28" transform="translate(109.68 18.28) rotate(180)"/>
              <rect x="9.68" y="81.72" width="90.32" height="18.28" transform="translate(145.7 36.02) rotate(90)"/>
              <rect x="101.08" y="81.72" width="90.32" height="18.28" transform="translate(237.1 -55.38) rotate(90)"/>
              <rect x="45.7" y="136.02" width="109.68" height="18.28" transform="translate(201.08 290.32) rotate(180)"/>
              <rect x="46.24" y="45.16" width="108.6" height="18.28" transform="translate(154.84 -46.24) rotate(90)"/>
              <rect x="137.1" width="18.28" height="18.28" transform="translate(155.38 -137.1) rotate(90)"/>
            
          </svg>
    </router-link>
    <span id="backprojects" class="anton">Projects</span>
    <div id="mouse">
      <div data-scroll-container class="container">
          <div class="section" data-scroll-section>
              <div>
                  <div data-scroll data-scroll-direction="horizontal"   data-scroll-speed="-6" >
                      <div class="donneesprojet">
                            <div class="projectname" > 
                              <span data-scroll data-scroll-call="1" data-scroll-repeat>Portfolio</span>
                              <span>Portfolio</span>
                            </div>
                            <div class="projectinfos">
                              <span class="projecttype">Projet personnel</span>
                              <span class="projectyear">2020-2021</span>
                              <span class="projecttechno">VueJs, LocomotiveScroll</span>
                            </div>
                      </div>
                      <div class="projet p1" v-on:click="portfolio">
                        <span class="montserratM">Go to website</span>
                      </div>
                      <p class="synopsis montserratM">Design, conception and development of my own website in order to present my personal projects.</p>
                  </div>
              </div>
          </div>
          <div class="section" data-scroll-section>
              <div>
                  <div data-scroll data-scroll-direction="horizontal"   data-scroll-speed="-6" >
                      <div class="donneesprojet">
                            <div class="projectname" > 
                              <span data-scroll data-scroll-call="2" data-scroll-repeat>Ebooks EMN</span>
                              <span>Ebooks EMN</span>
                            </div>
                            <div class="projectinfos">
                              <span class="projecttype">Projet collectif</span>
                              <span class="projectyear">2020-2021</span>
                              <span class="projecttechno">WordPress, WooCommerce</span>
                            </div>
                      </div>
                      <div class="projet p2" v-on:click="ebooks">
                        <span class="montserratM">Go to website</span>
                      </div>
                      <p class="synopsis montserratM">Development, technical design and online launch of an e-commerce website selling e-books ordered by an individual.</p>
                  </div>
              </div>
          </div>
          
          <div class="section" data-scroll-section>
              <div>
                  <div data-scroll data-scroll-direction="horizontal"   data-scroll-speed="-6" >
                      <div class="donneesprojet">
                            <div class="projectname" > 
                              <span data-scroll data-scroll-call="3" data-scroll-repeat>The Desktop</span>
                              <span>The Desktop</span>
                            </div>
                            <div class="projectinfos">
                              <span class="projecttype">Travail pratique</span>
                              <span class="projectyear">2021</span>
                              <span class="projecttechno">ThreeJS</span>
                            </div>
                      </div>
                      <div class="projet p3" v-on:click="bureau">
                        <span class="montserratM">Go to website</span>
                      </div>
                      <p class="synopsis montserratM">3D creation of our dream desktop as well as interaction coding within it.</p>
                  </div>
              </div>
          </div>
         <div class="section" data-scroll-section>
              <div>
                  <div data-scroll data-scroll-direction="horizontal"   data-scroll-speed="-6" >
                      <div class="donneesprojet">
                            <div class="projectname"> 
                              <span data-scroll data-scroll-call="4" data-scroll-repeat>Martin Scorsese</span>
                              <span>Martin Scorsese</span>
                            </div>
                            <div class="projectinfos">
                              <span class="projecttype">Examen</span>
                              <span class="projectyear">2021</span>
                              <span class="projecttechno">VueJs</span>
                            </div>
                      </div>
                      <div class="projet p4" v-on:click="boss">
                        <span class="montserratM">Go to website</span>
                      </div>
                      <p class="synopsis montserratM">Design, conception and development of a website relating the Martin Scorsese's biography and filmography within a time limit of 10 hours.</p>
                  </div>
              </div>
          </div>
          <div class="section" data-scroll-section>
              <div>
                  <div data-scroll data-scroll-direction="horizontal"   data-scroll-speed="-6" >
                      <div class="donneesprojet">
                            <div class="projectname" > 
                              <span data-scroll data-scroll-call="5" data-scroll-repeat>Wellspot</span>
                              <span>Wellspot</span>
                            </div>
                            <div class="projectinfos">
                              <span class="projecttype">Projet collectif</span>
                              <span class="projectyear">2020</span>
                              <span class="projecttechno">Php, Google Map API</span>
                            </div>
                      </div>
                      <div class="projet p5" v-on:click="wellspot">
                        <span class="montserratM">Go to website</span>
                      </div>
                      <p class="synopsis montserratM">Technical design and development of a web application allowing riders to share and find riding spot around them.</p>
                  </div>
              </div>
          </div>

          <div data-scroll-section id="property">
            <span data-scroll data-scroll-direction="horizontal" data-scroll-speed="-6" class="montserratM">All the creations above are the properties of Louis Cuenot.</span>
          </div>
          
          
        </div>
      </div>
      
    </div>
</template>

<script>
import {gsap} from 'gsap';
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
import LocomotiveScroll from 'locomotive-scroll';
export default {
    name: 'Projects',
    methods: {
      curs:function(event){
      var yh = event.clientY*100/window.innerHeight;
      var xl = event.clientX*100/window.innerWidth;
      var curs = document.querySelector(".curs");
      var curs2 = document.querySelector(".curs2");
      curs2.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
      curs.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
      },
      portfolio:function(){
        window.location.href="http://www.louiscuenot.com/"
      },
      ebooks:function(){
        window.location.href="https://thibaudhulin.net/"
      },
      bureau:function(){
        window.alert("This project is coming soon, don't be impatient !")
      },
      boss:function(){
        window.alert("This project is coming soon, don't be impatient !")
      },
      wellspot:function(){
        window.location.href="https://www.louiscuenot.com/wellspot/"
      },
        setScroll() {
          
            let scroller = new LocomotiveScroll({
                el:  document.querySelector('[data-scroll-container]'),
                smooth: true
            });
            
            gsap.registerPlugin(ScrollTrigger);
            scroller.on("scroll", ScrollTrigger.update);
            scroller.on("call", callValue => {
              var logo=document.getElementById('svg');
              var backp=document.getElementById('backprojects');
                if(callValue==="1"){
                  logo.style.fill="#ff4655";
                  backp.style="-webkit-text-stroke: #ff4655 3px;";
                }else if(callValue==="2"){
                  logo.style.fill="#FF69B4";
                  backp.style="-webkit-text-stroke: #FF69B4 3px;";
                }else if(callValue==="3"){
                  logo.style.fill="#BA55D3";
                  backp.style="-webkit-text-stroke: #BA55D3 3px;";
                }else if(callValue==="4"){
                  logo.style.fill="#FFD700";
                  backp.style="-webkit-text-stroke:#FFD700 3px;";
                }
                else if(callValue==="5"){
                  logo.style.fill="#DAA520";
                  backp.style="-webkit-text-stroke: #DAA520 3px;";
                  backp.innerText="Projects";
                }
                else if(callValue==="6"){
                  logo.style.fill="#ff4655";
                  backp.style="-webkit-text-stroke: #ff4655 3px;";
                  backp.innerText="Gallery";
                }
                
            });
            
            ScrollTrigger.scrollerProxy('.content ', {
               
                scrollTop(value) {
                    return arguments.length
                        ? scroller.scrollTo(value, 0, 0)
                        : scroller.scroll.instance.scroll.y;
                },
                getBoundingClientRect() {
                    return {
                        left: 0,
                        top: 0,
                        width: window.innerWidth,
                        height: window.innerHeight
                    };
                },
            });
            ScrollTrigger.addEventListener("enter", () =>{
              
                scroller.update()
                
                
            });
            ScrollTrigger.refresh();
            
        }
        
    },
    mounted() {
      if(document.querySelector('[data-scroll-container]')&& window.innerWidth>800){
        this.setScroll();
      }
        
    }
};
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Krona+One&display=swap');

 @media screen  and (orientation:landscape){

.container{
  width: 100vw;
  height: 100vh;
  height: min-content;
  overflow: scroll;
  background-image: url("~@/assets/bgw.png");
  background-size: cover;
}
 

  .section {
    height: 100vh;
    width: 70vw;
    margin: 0 0 15vh 10vw;
  }


  .section>div {
    display: flex;
    align-items: center;
    justify-content: left;
    width: 100%;
    height: 100%;
    
  }

  .projet{
    width: 20%;
    height:50%;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    transition:1s;
  }

  .projet:hover{
    transform: scale(1.1);
  }

  
  .projet>span{
    width: 0;
    height: 30%;
    overflow: hidden;
    transition: 1s;
    font-size: 70%;
    white-space: nowrap;
    padding-top: 5%;
    transform: translateY(45%);
    text-transform: uppercase;
    border-top: #ff4655 1px solid;
  }
  

  .projet:hover>span{
    width: 55%;
    height: 30%;
    text-align: center;
    overflow: hidden;
    color: #345370;
    border-top: #ff4655 1px solid;
    padding-top: 5%;
    transform: translateY(45%);
    font-size: 70%;
  }

  

  .synopsis{
    width: 30%;
    color: #284e72;
    font-size: 2.4vh;
    line-height: 3vh;
  }


  .p1{
    background:url("~@/assets/logo.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p2{
    background:url("~@/assets/LogoEbooks.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p3{
    background:url("~@/assets/logo.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p4{
    background:url("~@/assets/LogoBoss.svg");
    background-size: auto 50% ;
    background-repeat: no-repeat;
    background-position:center ;
  }

  .p5{
    background:url("~@/assets/LogoWellspot.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }



  .section>div>div{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 70vw;
    height: 50%;
    border-left:5px solid #ff4655;
    padding-left: 5%;
  }

  .donneesprojet{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 20%;
    height: 80%;
  }
  

  

  .projectname{
    display: flex;
    flex-direction: column;
    justify-content: center; 
    height: 40%;
    width: 100%;
  }


  

  .projectname>span{
    font-size: 4.3vh;
    font-family: 'Krona One', sans-serif;
    text-transform: uppercase;
    color: #284e72;
  }

  .projectname>span:last-of-type{
    transform: rotateX(180deg);
    color: #1b2d3e;
  }

  .projectinfos{
    display: flex;
    flex-direction: column;
    height: 40%;
    width: 100%;
    justify-content: space-between;
  }

  .projectinfos>span{
    font-family: 'Montserrat',sans-serif;
    font-size: 2vh;
    color: #284e72;
  }

  #logo{
    position: fixed;
    top: 2vw;
    left: 2.6vw;
    width: 8vh;
    height: 8vh;
    z-index: 9;
    cursor: none;
    transition:0.25s;
  }

  #logo>svg{
    transition: 0.5s;
  }

  #logo:hover{
    transform: scale(1.1);
  }

  #backprojects{
    position: fixed;
    bottom: 2vw;
    right:2.6vw;
    writing-mode: vertical-lr;
    font-size: 12vh;
    -webkit-text-stroke: 3px #345370;
    color: transparent;
    transition:0.5s;
    z-index: 9;
  }

  #property{
    width: 100vw;
    height: min-content;
    display: flex;
    justify-content: center;
  }

  #property>span{
    color: #284e72;
    text-transform: uppercase;
    font-size: 10px;
  }

  

 }

  @media screen  and (orientation:portrait){

.container{
  width: 100vw;
  height: 100vh;
  height: min-content;
  overflow-y: scroll;
  background-image: url("~@/assets/bgw.png");
  background-size: cover;
}
 

  .section {
    height: 100vh;
    width: 100vw;
    margin: 10vh 0 0 10vw;
  }


  .section>div {
    display: flex;
    align-items: center;
    justify-content:left;
    width: 100%;
    height: 100%;
  }
  

  .projet{
    width: 100%;
    height:30%;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    transition:1s;
  }

  .projet:hover{
    transform: scale(1.1);
  }

  
  .projet>span{
    width: 0;
    height: 30%;
    overflow: hidden;
    transition: 1s;
    font-size: 70%;
    white-space: nowrap;
    padding-top: 5%;
    transform: translateY(45%);
    text-transform: uppercase;
    border-top: #ff4655 1px solid;
  }
  

  .projet:hover>span{
    width: 55%;
    height: 30%;
    text-align: center;
    overflow: hidden;
    color: #345370;
    border-top: #ff4655 1px solid;
    padding-top: 5%;
    transform: translateY(45%);
    font-size: 70%;
  }

  

  .synopsis{
    width: 80%;
    height: 20%;
    color: #284e72;
    font-size: 2.4vh;
    line-height: 3vh;
  }


  .p1{
    background:url("~@/assets/logo.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p2{
    background:url("~@/assets/LogoEbooks.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p3{
    background:url("~@/assets/logo.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }

  .p4{
    background:url("~@/assets/LogoBoss.svg");
    background-size: auto 50% ;
    background-repeat: no-repeat;
    background-position:center ;
  }

  .p5{
    background:url("~@/assets/LogoWellspot.svg");
    background-size: auto 50%;
    background-repeat: no-repeat;
    background-position: center;
  }



  .section>div>div{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 50vw;
    height: 80%;
    border-left:3px solid #ff4655;
    padding-left: 5%;
    
  }

  .donneesprojet{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 100%;
    height: 50%;
  }

  

  .projectname{
    display: flex;
    flex-direction: column;
    justify-content: center; 
    height: 40%;
    width: 100%;
  }

  

  .projectname>span{
    font-size: 3.3vh;
    font-family: 'Krona One', sans-serif;
    text-transform: uppercase;
    color: #284e72;
  }

  .projectname>span:last-of-type{
    transform: rotateX(180deg);
    color: #1b2d3e;
  }

  .projectinfos{
    display: flex;
    flex-direction: column;
    height: 50%;
    width: 100%;
    justify-content: space-between;
  }

  .projectinfos>span{
    font-family: 'Montserrat',sans-serif;
    font-size: 2.4vh;
    color: #284e72;
  }

  #logo{
    position: fixed;
    top: 2vw;
    left: 2.6vw;
    width: 8vh;
    height: 8vh;
    z-index: 9;
    cursor: none;
    transition:0.25s;
  }

  #logo>svg{
    transition: 0.5s;
  }

  #logo:hover{
    transform: scale(1.1);
  }

  #backprojects{
    position: fixed;
    bottom: 2vw;
    right:2.6vw;
    writing-mode: vertical-lr;
    font-size: 9vh;
    -webkit-text-stroke: 2px #345370;
    color: transparent;
    transition:0.5s;
    z-index: 9;
  }

 }

</style>