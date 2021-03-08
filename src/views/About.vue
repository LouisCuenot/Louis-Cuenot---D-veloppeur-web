<template>
    <div v-show="show" transition="test" class="transiton"></div>
  <div class="body" v-on:mousemove="coord">
    <div id="bgabout">
        <div id="mvmnt" class="laptop"></div>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svgaboutlaptop" class="laptop">
            <line id="lignaboutonelaptop" x1="7.5%" x2="7.5%" y1="0" y2="95.5%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignabouttwolaptop" x1="0" x2="20%" y1="87%" y2="87%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
        </svg>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svgaboutlaptop" class="landscape">
            <line id="lignaboutonelaptop" x1="7.5%" x2="7.5%" y1="0" y2="95.5%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignabouttwolaptop" x1="0" x2="20%" y1="87%" y2="87%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
        </svg>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svgaboutportrait" class="portrait">
            <line id="lignaboutoneportrait" x1="12%" x2="12%" y1="0" y2="21%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
            <line id="lignabouttwoportrait" x1="0" x2="24%" y1="17%" y2="17%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
        </svg>
        <section id="about" class="white">

            <div class="hb zi" v-on:click="openmenuabout">
                <div class="hbrgr"></div>
            </div>

            <nav class="montserratM uppercase white zi">
                    <router-link to="/" class="white">Home</router-link>
                    <router-link to="/projects" class="white">Projects</router-link>
                    <router-link to="/about" class="white">About</router-link>
                <svg  xmlns="http://www.w3.org/2000/svg" class="laptop">
                    <line x1="87%" x2="100%" y1="80%" y2="80%" fill="transparent" stroke="#FF4655" stroke-width="4"/>
                </svg>
                <svg  xmlns="http://www.w3.org/2000/svg" class="portrait">
                    <line x1="5%" x2="22%" y1="60%" y2="60%" fill="transparent" stroke="#FF4655" stroke-width="4"/>
                </svg>
                <svg  xmlns="http://www.w3.org/2000/svg" class="landscape">
                    <line x1="5%" x2="14%" y1="71%" y2="71%" fill="transparent" stroke="#FF4655" stroke-width="4"/>
                </svg>
            </nav>
            <ul>
                <li><span>Hi</span>, i'm</li>
                <li>Louis Cuenot,</li>
                <li>a passionate</li>
                <li>web developper</li>
              </ul>
            <div class="socials">
                <router-link to="/Contact"></router-link>
                <a href="https://www.linkedin.com/in/louis-cuenot-7a7b141a2/"></a>
                <a href="https://www.facebook.com/louis.cuenot.79"></a>
                <a href="https://www.instagram.com/louiscuenot/?hl=fr"></a>
            </div>
            <div id="buttonhome">
                <router-link to="/"></router-link>
            </div>
            <div id="lhead">
                <img src="../assets/lhead.svg" alt="" id="head">
            </div>
            <span id="backabout" class="anton">About</span>
            <router-link to="/Contact" class="staatliches white uppercase">Contact</router-link>
        </section>
    </div>    
  </div>
</template>

<script>
export default {
  name: 'About',
  methods:{
    coord:function(event){
      var croix = document.getElementById('mvmnt');
      var yh = event.clientY*100/window.innerHeight;
      var xl = event.clientX*100/window.innerWidth;
      var angley = (yh-50)/500;
      var anglex = (xl-50)/500;
      croix.style.transform="rotateX("+angley+"rad) rotateY("+anglex+"rad)";
        var heady = (yh-70)/150;
        var headx = (xl-70)/150;
        var head = document.getElementById('head');
        head.style.transform="rotateX("+heady+"rad) rotateY("+headx+"rad)";
        var curs = document.querySelector(".curs");
        var curs2 = document.querySelector(".curs2");
        curs2.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
        curs.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
    },
    openmenuabout:function(){
      var hb = document.querySelector('.hb');
      hb.classList.toggle('active-one');
      var nav = document.querySelector('nav');
      nav.classList.toggle('open');
      var backA = document.getElementById('backabout');
      backA.classList.toggle('backaboutfront');
    }
  }
}
</script>

<style scoped>


    

    .test-enter{
        animation: width-in ease 5s;
    }

    .test-leave{
        animation: width-out ease 5s;
    }

    @keyframes width-in {
        0%{
            position: absolute;
            width: 100vw;
            height: 100vh;
            background-color: yellow;
            z-index: 100;
        }
        100%{
            position: absolute;
            width: 0;
            height: 100vh;
            background-color: yellow;
            z-index: 100;
        }
    }

    @keyframes width-out {
        0%{
            position: absolute;
            width: 0;
            height: 100vh;
            background-color: yellow;
            z-index: 100;
        }
        100%{
            position: absolute;
            width: 100vw;
            height: 100vh;
            background-color: yellow;
            z-index: 100;
        }
    }
    

    
  @media screen and (min-width:1000px) and (orientation:landscape){

    .hb{
        display: none;
    }


    .portrait{
        display: none;
    }

    .landscape{
        display: none;
    }

    #svgaboutlaptop{
        position: absolute;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
    }

    #lignaboutonelaptop{
        stroke-dasharray: 1300;
        stroke-dashoffset: 1300;
        animation: dash 3s ease forwards;
    }

    #lignabouttwolaptop{
        stroke-dasharray: 500;
        stroke-dashoffset: 500;
        animation: dash 2.4s ease forwards;
    }

    nav>svg>line{
        stroke-dasharray: 400;
        stroke-dashoffset: 500;
        animation: dash 3s ease forwards;
    }



    @keyframes dash {
        to{
            stroke-dashoffset: 0;
        }
    }

   
   
    .body{
        background: url("~@/assets/bg.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        width: 100vw;
        height: 100vh;
        -webkit-perspective: 500px;
        -moz-perspective: 500px;
        -o-perspective: 500px;
        perspective: 500px;
    }

    div#bgabout{
        width: 100%;
        height: 100%;
    }



    div#mvmnt{
        position: absolute;
        width: 97vw;
        height: 97vh;
        z-index: 10;
        background-image: url(~@/assets/backabout.png); 
        background-size: 85%;
        background-repeat: no-repeat;
        background-position: center;
        pointer-events: none;
    }

    section#about{
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-rows: 13.9vh 6.25vh 29.85vh 29vh 1fr;
        grid-template-columns: 9.63vw 2.34vw 41.4vw 4.95vw 1fr;
        transform: translateX(-10%); 
        opacity: 0;
        animation: opac 1s linear forwards;
    }



    @keyframes opac{
        from{
            transform: translateX(-10%);  
        }
    
        to{
            transform: translateX(0);
            opacity: 1;
        }
}

    section#about nav{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        flex-wrap: nowrap;
        width:30vw;
        height: 4vh;
        grid-row-start: 2;
        grid-column-start: 2;
        grid-column-end: 4;
        font-size: 2vh;
    }


    section#about nav a{
        font-size: 2.4vh;
        z-index: 2;
        transition: 0.5s;
    }

    section#about nav a:hover{
        color: #FF4655;
    }

    section#about nav svg{
        position: absolute;
        width: 30vw;
        height: 3vh;
        transform: translateX(2%);
        z-index: 1;
    }

    section#about>ul{
        grid-column-start: 2;
        grid-row-start:3;
        grid-row-end: 5;
        width: 37vw;
        padding: 0;
        padding-left: 30px;
        margin: 0;
        font-family: Staatliches,sans-serif;
        text-transform: uppercase;
        transform: translate3d(0, 0, 0);
        
    }

    li{
        height: 50px;
        list-style: none;
        position: relative;
        font-size: 50px;
        font-weight:500;
        padding-left: 7px;   
           
    }

    li>span{
        color: #FF4655;
    }
    li:nth-child(odd) {
        transform: skew(40deg, -20deg) scaleY(0.9) translateX(-5%);
        text-shadow: -6px 3px 5px black;
    }
    li:nth-child(even) {
        transform: skew(0deg, -20deg) scaleY(1.2) translateX(-5%);
        text-shadow: -4px -4px 5px black;
    }
    li:nth-child(1) {
        left: 29px;
    }
    li:nth-child(2) {
        left: 50px;
    }
    li:nth-child(3) {
        left: 60px;
    }
    li:nth-child(4) {
        left: 80px;
        color: #FF4655;
    }

    section#about .socials{
        grid-column-start: 3;
        grid-row-start: 5;
        width: 20vw;
        height: 5vh;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
        overflow: visible;
    }

    section#about .socials>a{
        width: 20%;
        height: 90%;
        background-repeat: no-repeat;
        background-size:auto 100%;
        background-position: bottom;
        transition: 0.5s;
    }

    section#about .socials>a:nth-child(1){
        background-image: url(~@/assets/mail.svg);
    }

    section#about .socials>a:nth-child(1):hover{
        background-image:url(~@/assets/mailred.svg) ;
        width: 26%;
        transform: scale(1.15);
    }  

    section#about .socials>a:nth-child(2){
        background-image: url(~@/assets/linkedin.svg);
    }

    section#about .socials>a:nth-child(2):hover{
        background-image:url(~@/assets/linkedinred.svg) ;
        width: 26%;
        transform: scale(1.15);
    }  

    section#about .socials>a:nth-child(3){
        background-image: url(~@/assets/facebook.svg);
    }

    section#about .socials>a:nth-child(3):hover{
        background-image:url(~@/assets/facebookred.svg) ;
        width: 26%;
        transform: scale(1.25);
    }  

    section#about .socials>a:nth-child(4){
        background-image: url(~@/assets/instagram.svg);
    }

    section#about .socials>a:nth-child(4):hover{
        background-image:url(~@/assets/instagramred.svg) ;
        width: 26%;
        transform: scale(1.25);
    }  

    section#about #lhead{
        grid-column-start: 4;
        grid-column-end: 6;
        grid-row-start: 1;
        grid-row-end: 6;
        background-color: #FF4655;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        box-shadow:-20px 0 1em #1B2D3E;
        transform: translateX(50vw);
        animation: lhead 1.1s ease-in forwards;
    }

    @keyframes lhead {
        from{
            transform: translateX(50vw) scale(1);
        }
        to{
            transform: translateX(0) scale(1);
        }
    }

    section#about #lhead img{
        width: 70%;
    }

    section#about #backabout{
        grid-column-start: 5;
        grid-row-start: 1;
        grid-row-end: 4;
        justify-self: end;
        color: transparent;
        text-transform: uppercase;
        font-size: 25vh;
        -webkit-text-stroke: 5px;
        -webkit-text-stroke-color: #9B131E;
        animation: lhead 1.5s ease-in forwards;
    }

    section#about #buttonhome{
        grid-column-start: 4;
        grid-row-start: 4;
        box-shadow:-20px 0 1em #1B2D3E ;
        width:5.2vw;
        height: 5.2vw;
        background-color:#F3F1EE ;
        z-index: 13;
        cursor: pointer;
        border: #FF4655 solid 6px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        transform: translateX(50vw) translateY(-50%);
        animation: btnhome 1.1s ease-in forwards;
    }

    @keyframes btnhome {
        from{
            transform: translateY(-50%) translateX(50vw);
        }
        to{
            transform: translateY(-50%) translateX(-50%);
        }
    }

    section#about #buttonhome a{
        width: 100%;
        height: 100%;
        background-image: url(~@/assets/home.svg);
        background-size: 60% 60%;  
        background-repeat: no-repeat; 
        background-position: center center;       
    }

    section#about #buttonhome:hover a{
        animation: hoverhome 900ms linear infinite;
    }

    @keyframes hoverhome {
        
        50%{
            transform: scale(1.1);
        }
       
        100%{
            transform: scale(1);
        }   
    }

    #about>a{
        grid-column-start:5;
        grid-row-start: 1;
        z-index: 10;
        align-self: end;
        font-size: 3vh;
        padding:0 10px;
        width: max-content;
        border: #9B131E solid 2px;
        transition: 0.3s;
        letter-spacing: 1px;
        animation: lhead 1.1s ease-in forwards;
    }

    #about>a:hover{
        color: transparent;
        background-color: #9B131E;
        -webkit-text-stroke: 2px;
        -webkit-text-stroke-color: #D2CECA;
        font-size: 3.5vh;
    }


}

@media screen and (orientation:portrait) {

    .body{
        background: url("~@/assets/bg.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        width: 100vw;
        height: 100vh;
        -webkit-perspective: 500px;
        -moz-perspective: 500px;
        -o-perspective: 500px;
        perspective: 500px;
    }

    .hbrgr{
        top:50%;
        left:10%;
        width: 40px;
        height: 4px;
        background: #D2CECA;
        position: relative;
        box-shadow: 0 2px 5px rgba(0, 0, 0, .2);
        transition: 0.5s;
        overflow: visible;
      }
      
      .hbrgr:before {
        top: -16px;
        width: 50px;
      }
      
      .hbrgr:after {
        top: 16px;
        width: 30px;
      }

      .hb {
        width: 40px;
        height: 40px;
        cursor: pointer;
        overflow: visible;
        grid-column-start: 2;
        grid-row-start: 2;
        z-index: 100;
        
      }

      .hbrgr:before,.hbrgr:after {
            content: '';
            position:absolute;
            height: 4px;
            background:#D2CECA;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition:0.5s;
        }

        .hb.active-one .hbrgr{
            background:rgba(0,0,0,0);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0);
            width: 50px;
          }
          
          .hb.active-one .hbrgr:before {
            top: 0;
            transform:rotate(45deg);
            background: #1B2D3E;
          }
          
          .hb.active-one .hbrgr:after {
            top: 0;
            transform:rotate(135deg);
            box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.2);
            width: 50px;
            background: #1B2D3E;
          }


          .laptop{
              display: none;
          }

          .landscape{
              display: none;
          }

          section#about nav{
            grid-column-start: 1;
            grid-row-start: 1;
            width: 100vw;
            height: 100vh;
            background-color: #eeeeee;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: left;
            padding-left: 15vw;
            transform: translateX(-100%);
            z-index: 80;
            animation: navoff 600ms ease-out;
            position: absolute;
            top: 0;
            left: 0;
        }

        section#about nav.open{
            transform: translateX(0);
            animation: nav 600ms ease-out;
        }

        
            
        @keyframes nav {
            from{
                transform: translateX(-100%);
            }
            to{
                transform: translateX(0);
            }
        }

        @keyframes navoff {
          from{
              transform: translateX(0);
          }
          to{
              transform: translateX(-100%);
          }
      }

        section#about nav a{
            color:#1B2D3E;
            margin-bottom: 7vh;
            font-size: 3vh;
            z-index: 83;
        }

        #svgaboutportrait{
            position: absolute;
            left: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
        }

        #lignaboutoneportrait{
            stroke-dasharray: 1300;
            stroke-dashoffset: 1300;
            animation: dash 3s ease forwards;
        }
    
        #lignabouttwoportrait{
            stroke-dasharray: 500;
            stroke-dashoffset: 500;
            animation: dash 2.4s ease forwards;
        }
    
    
        @keyframes dash {
            to{
                stroke-dashoffset: 0;
            }
        }

        section#about{
            position: absolute;
            top: 0;
            left: 0;
            height: 100vh;
            width: 100vw;
            display: grid;
            grid-template-columns: 7.48vw 38.47vw 1fr;
            grid-template-rows: 4.2vh 12.5vh 40.4vh 10.2vh 1fr;
            opacity: 0;
              animation: opac 1.1s ease forwards;
              transform: translateY(-10%);
          }

          @keyframes opac{
            from{
                transform: translateY(-10%);  
            }
        
            to{
                transform: translateY(0);
                opacity: 1;
            }
        }

        section#about #backabout{
            grid-column-start: 3;
            grid-row-start: 2;
            font-size: 14vh;
            text-transform: uppercase;
            height: max-content;
            width: max-content;
            -webkit-text-stroke: 4px;
            -webkit-text-stroke-color: #345370;
            color: transparent;
            z-index: -1;
      }

  section#about>ul{
        grid-column-start: 2;
        grid-row-start:3;
        width: 80vw;
        padding: 0;
        margin: 0;
        font-family: Staatliches,sans-serif;
        text-transform: uppercase;
        transform: translate3d(0, 0, 0);
    }

    li{
        height: 35px;
        list-style: none;
        position: relative;
        font-size: 35px;
        font-weight:500;
        line-height: 27px;
        padding-left: 15px;
    }

    li>span{
        color: #FF4655;
    }

    li:nth-child(odd) {
        transform: skew(40deg, -20deg) scaleY(0.9) translateX(-7%);
        text-shadow: -6px 3px 5px black;
    }
    li:nth-child(even) {
        transform: skew(0deg, -20deg) scaleY(1.2) translateX(-7%);
        text-shadow: -4px -4px 5px black;
    }
    li:nth-child(1) {
        left: 29px;
    }
    li:nth-child(2) {
        left: 38px;
    }
    li:nth-child(3) {
        left: 50px;
    }
    li:nth-child(4) {
        left: 59px;
        color: #FF4655;
    }

    section#about .socials{
        grid-column-start: 3;
        grid-row-start: 4;
        width: 40vw;
        height: 4.2vh;
        
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
    }

    section#about .socials>a{
        width: 20%;
        height: 90%;
        cursor: pointer;
        background-repeat: no-repeat;
        background-size: auto 90%;
        align-self: flex-end;
       
    }

    section#about .socials>a:nth-child(1){
        background-image: url(~@/assets/mail.svg);
    }

    section#about .socials>a:nth-child(2){
        background-image: url(~@/assets/linkedin.svg);
    }

    section#about .socials>a:nth-child(3){
        background-image: url(~@/assets/facebook.svg);
    }

    section#about .socials>a:nth-child(4){
        background-image: url(~@/assets/instagram.svg);
    }

    
    section#about #lhead{
        grid-column-start: 1;
        grid-column-end: 4;
        grid-row-start: 5;
        grid-row-end: 6;
        background-color: #FF4655;
        padding-right: 7vw;
        display: flex;
        flex-direction: row;
        justify-content: flex-end;
        align-items: center;
        box-shadow: 0 -20px 1em #1B2D3E;
        animation: lhead 1.1s ease-in forwards;
        transform: translateY(100%);
    }


    @keyframes lhead {
        from{
            transform: translateY(100%);
        }
        to{
            transform: translateY(0);
        }
    }

    section#about #buttonhome{
        grid-column-start: 1;
        grid-row-start: 5;
        box-shadow: 0 -20px 1em #1B2D3E ;
        width:14vw;
        height: 14vw;
        background-color:#F3F1EE ;
        z-index: 13;
        cursor: pointer;
        border: #FF4655 solid 6px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        transform: translateY(50vh);
        animation: btnabout 1.3s ease-in forwards;
    }

    @keyframes btnabout {
        from{
            transform:translateY(50vh);
        }
        to{
            transform: translateY(-50%);
        }
    }

    section#about #buttonhome a{
        width: 100%;
        height: 100%;
        background-image: url(~@/assets/home.svg);
        background-size: 60% 60%;  
        background-repeat: no-repeat; 
        background-position: center center;       
    }

    section#about #buttonhome:hover a{
        animation: hoverhome 900ms linear infinite;
    }

    section#about #lhead img{
        height:85%;
    }

    section#about #backabout.backaboutfront{
        z-index: 81;
        animation: colorback 600ms linear;
        -webkit-text-stroke-color:#DFDFDF;
    }

    @keyframes colorback {
        from{
          -webkit-text-stroke-color:#345370;
        }
        to{
          -webkit-text-stroke-color:#DFDFDF;
        }
    }

    section#about nav svg.portrait{
        position: absolute;
        width: 100vw;
        height: 100vh;
        z-index: 82;
    }

    #about>a{
        grid-column-start:2;
        grid-row-start: 5;
        z-index: 10;
        align-self: end;
        font-size: 3vh;
        padding:0 10px;
        width: max-content;
        border: #9B131E solid 2px;
        transition: 0.3s;
        letter-spacing: 1px;
        animation: lhead 1.1s ease-in forwards;
        align-self:center;
    }


}

@media screen and (max-width:999px) and (orientation:landscape){

    #mvmnt{
        display: none;
    }
    
    .hbrgr{
        top:50%;
        left:10%;
        width: 40px;
        height: 4px;
        background: #D2CECA;
        position: relative;
        box-shadow: 0 2px 5px rgba(0, 0, 0, .2);
        transition: 0.5s;
        overflow: visible;
      }
      
      .hbrgr:before {
        top: -16px;
        width: 50px;
      }
      
      .hbrgr:after {
        top: 16px;
        width: 30px;
      }

      .hb {
        width: 40px;
        height: 40px;
        cursor: pointer;
        overflow: visible;
        grid-column-start: 2;
        grid-row-start: 2;
        z-index: 100;
        
      }

      .hbrgr:before,.hbrgr:after {
            content: '';
            position:absolute;
            height: 4px;
            background:#D2CECA;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition:0.5s;
        }

        .hb.active-one .hbrgr{
            background:rgba(0,0,0,0);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0);
            width: 50px;
          }
          
          .hb.active-one .hbrgr:before {
            top: 0;
            transform:rotate(45deg);
            background: #1B2D3E;
          }
          
          .hb.active-one .hbrgr:after {
            top: 0;
            transform:rotate(135deg);
            box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.2);
            width: 50px;
            background: #1B2D3E;
          }

          section#about nav{
            grid-column-start: 1;
            grid-row-start: 1;
            width: 100vw;
            height: 100vh;
            background-color: #eeeeee;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: left;
            padding-left: 15vw;
            transform: translateY(-100%);
            animation: navoff 600ms ease-out;
            z-index: 81;
        }

        section#about nav.open{
            transform: translateX(0);
            
            animation: nav 600ms ease-out;
        }

        
            
        @keyframes nav {
            from{
                transform: translateY(-100%);
            }
            to{
                transform: translateY(0);
            }
        }

        @keyframes navoff {
          from{
              transform: translateY(0);
          }
          to{
              transform: translateY(-100%);
          }
      }

      section#about nav a{
        color:#1B2D3E;
        margin-top: 7vh;
        font-size: 5vh;
        z-index: 82;
    }

    section#about nav svg.landscape{
        position: absolute;
        width: 100vw;
        height: 100vh;
    }

    section#about #backabout.backaboutfront{
        z-index: 81;
        animation: colorback 600ms linear;
        -webkit-text-stroke-color:#DFDFDF;
    }

    @keyframes colorback {
        from{
        -webkit-text-stroke-color: #9B131E;
        }
        to{
          -webkit-text-stroke-color:#DFDFDF;
        }
    }

    .portrait{
        display: none;
    }

    .laptop{
        display: none;
    }

    #svgaboutlaptop{
        position: absolute;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
    }

    #lignaboutonelaptop{
        stroke-dasharray: 1300;
        stroke-dashoffset: 1300;
        animation: dash 3s ease forwards;
    }

    #lignabouttwolaptop{
        stroke-dasharray: 500;
        stroke-dashoffset: 500;
        animation: dash 2.4s ease forwards;
    }

    nav>svg>line{
        stroke-dasharray: 400;
        stroke-dashoffset: 500;
        animation: dash 3s ease forwards;
    }



    @keyframes dash {
        to{
            stroke-dashoffset: 0;
        }
    }

   
   
    .body{
        background: url("~@/assets/bg.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        width: 100vw;
        height: 100vh;
        -webkit-perspective: 500px;
        -moz-perspective: 500px;
        -o-perspective: 500px;
        perspective: 500px;
    }

    div#bgabout{
        width: 100%;
        height: 100%;
    }



    div#mvmnt{
        position: absolute;
        width: 97vw;
        height: 97vh;
        z-index: 10;
        background-image: url(~@/assets/backabout.png);  
        background-size: 85%;
        background-repeat: no-repeat;
        background-position: center;
        pointer-events: none;
    }

    section#about{
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-rows: 10.9vh 10.25vh 28.85vh 25.5vh 1fr;
        grid-template-columns: 9.63vw 2.34vw 41.4vw 4.95vw 1fr;
        transform: translateX(-10%); 
        opacity: 0;
        animation: opac 1s linear forwards;
    }



    @keyframes opac{
        from{
            transform: translateX(-10%);  
        }
    
        to{
            transform: translateX(0);
            opacity: 1;
        }
}

section#about>ul{
    grid-column-start: 2;
    grid-row-start:3;
    grid-row-end: 5;
    width: 40vw;
    padding: 0;
    margin: 0;
    font-family: Staatliches,sans-serif;
    text-transform: uppercase;
    transform: translate3d(-10px, 0, 0);
    
}

li{
    width: 80%;
    height: 30px;
    list-style: none;
    position: relative;
    font-size: 30px;
    font-weight:500;
    padding-left: 5px;
}

li>span{
    color: #FF4655;
}
li:nth-child(odd) {
    transform: skew(40deg, -20deg) scaleY(0.9) translateX(-5%);
    text-shadow: -6px 3px 5px black;
}
li:nth-child(even) {
    transform: skew(0deg, -20deg) scaleY(1.2) translateX(-5%);
    text-shadow: -4px -4px 5px black;
}
li:nth-child(1) {
    left: 29px;
}
li:nth-child(2) {
    left: 44px;
}
li:nth-child(3) {
    left: 56px;
}
li:nth-child(4) {
    left: 70px;
    color: #FF4655;
}

    section#about .socials{
        grid-column-start: 3;
        grid-row-start: 5;
        width: 23vw;
        height: 6vh;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
    }

    section#about .socials>a{
        width: 20%;
        max-height: 90%;
        background-repeat: no-repeat;
        background-size: auto 90%  ;
        background-position: bottom;
    }

    section#about .socials>a:nth-child(1){
        background-image: url(~@/assets/mail.svg);
    }

    section#about .socials>a:nth-child(1):hover{
        background-image:url(~@/assets/mailred.svg) ;
    }  

    section#about .socials>a:nth-child(2){
        background-image: url(~@/assets/linkedin.svg);
    }

    section#about .socials>a:nth-child(2):hover{
        background-image:url(~@/assets/linkedinred.svg) ;
    }  

    section#about .socials>a:nth-child(3){
        background-image: url(~@/assets/facebook.svg);
    }

    section#about .socials>a:nth-child(3):hover{
        background-image:url(~@/assets/facebookred.svg) ;
    }  

    section#about .socials>a:nth-child(4){
        background-image: url(~@/assets/instagram.svg);
    }

    section#about .socials>a:nth-child(4):hover{
        background-image:url(~@/assets/instagramred.svg) ;
    }  

    section#about #lhead{
        grid-column-start: 4;
        grid-column-end: 6;
        grid-row-start: 1;
        grid-row-end: 6;
        background-color: #FF4655;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        box-shadow:-20px 0 1em #1B2D3E;
        transform: translateX(50vw);
        animation: lhead 1.1s ease-in forwards;
    }

    @keyframes lhead {
        from{
            transform: translateX(50vw);
        }
        to{
            transform: translateX(0);
        }
    }

    section#about #lhead img{
        width: 70%;
    }

    section#about #backabout{
        grid-column-start: 5;
        grid-row-start: 1;
        grid-row-end: 4;
        justify-self: end;
        color: transparent;
        text-transform: uppercase;
        font-size: 19vh;
        -webkit-text-stroke: 5px;
        -webkit-text-stroke-color: #9B131E;
        animation: lhead 1.5s ease-in forwards;
    }

    section#about #buttonhome{
        grid-column-start: 4;
        grid-row-start: 4;
        box-shadow:-20px 0 1em #1B2D3E ;
        width:5.2vw;
        height: 5.2vw;
        background-color:#F3F1EE ;
        z-index: 13;
        cursor: pointer;
        border: #FF4655 solid 6px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        transform: translateX(50vw) translateY(-50%);
        animation: btnhome 1.1s ease-in forwards;
    }

    @keyframes btnhome {
        from{
            transform: translateY(-50%) translateX(50vw);
        }
        to{
            transform: translateY(-50%) translateX(-50%);
        }
    }

    section#about #buttonhome a{
        width: 100%;
        height: 100%;
        background-image: url(~@/assets/home.svg);
        background-size: 60% 60%;  
        background-repeat: no-repeat; 
        background-position: center center;       
    }

    section#about #buttonhome:hover a{
        animation: hoverhome 900ms linear infinite;
    }

    @keyframes hoverhome {
        
        50%{
            transform: scale(1.1);
        }
       
        100%{
            transform: scale(1);
        }   
    }

        #about>a{
        position: absolute;
        right: 5vw;
        bottom: 5vh;
        z-index: 10;
        align-self: end;
        font-size: 3vh;
        padding:0 10px;
        width: max-content;
        border: #9B131E solid 2px;
        transition: 0.3s;
        letter-spacing: 1px;
        animation: lhead 1.1s ease-in forwards;
    }

}
</style>
