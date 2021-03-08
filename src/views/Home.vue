<template>
<div class="body" v-on:mousemove="coord">
    <div id="bghome">
        <div id="mvmnt" class="laptop"></div>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svghomelaptop" class="laptop">
            <line id="lignhomeonelaptop" x1="7%" x2="7%" y1="0" y2="95%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhometwolaptop" x1="3%" x2="100%" y1="87%" y2="88%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhomethreelaptop" x1="0" x2="10%" y1="12%" y2="12%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
        </svg>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svghomeportrait" class="portrait">
            <line id="lignhomeoneportrait" x1="0" x2="23%" y1="8%" y2="8%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
            <line id="lignhometwoportrait" x1="90%" x2="90%" y1="0" y2="12%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhomethreeportrait" x1="9.6%" x2="9.6%" y1="72%" y2="100%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhomefourportrait" x1="0" x2="60%" y1="94%" y2="94%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
        </svg>
        <svg  xmlns="http://www.w3.org/2000/svg" id="svghomelandscape" class="landscape">
            <line id="lignhomeonelandscape" x1="7.45%" x2="7.45%" y1="0" y2="25.8%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
            <line id="lignhometwolandscape" x1="0" x2="92%" y1="93%" y2="93%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhomethreelandscape" x1="90%" x2="100%" y1="10%" y2="10%" fill="transparent" stroke="#D2CECA" stroke-width="3"/>
            <line id="lignhomefourlandscape" x1="87%" x2="87%" y1="85%" y2="100%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
        </svg>
        <section id="home" class="white">
            <div class="hb zi" v-on:click="openmenuhome">
                <div class="hbrgr"></div>
            </div>
            <nav class="montserratM uppercase white zi">
                    <router-link to="/" class="white">Home</router-link>
                    <router-link to="/projects" class="white">Projects</router-link>
                    <router-link to="/about" class="white">About</router-link>
                    <svg xmlns="http://www.w3.org/2000/svg" class="laptop">
                        <line x1="5%" x2="100%" y1="0" y2="0" fill="transparent" stroke="#FF4655" stroke-width="5"/>
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" class="portrait">
                        <line x1="5%" x2="17%" y1="38%" y2="38%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" class="landscape">
                        <line x1="3%" x2="13%" y1="44%" y2="44%" fill="transparent" stroke="#FF4655" stroke-width="3"/>
                    </svg>
            </nav>
            <router-link class="staatliches" to="/Contact">Contact</router-link>
            <div id="titreA">
                <h1 class="staatliches">Louis <br/>Cuenot</h1>
                <svg xmlns="http://www.w3.org/2000/svg">
                <line x1="20%" x2="110%" y1="0" y2="0" fill="transparent" stroke="#FF4655" stroke-width="50"/>
                </svg>
            </div>
            <h2 class="kanitT">Apprentice web developer</h2>
            <span id="backhome" class="anton uppercase">Home</span>
            <p id="text" class="white montserratM"></p>
        </section>
    </div>
</div>
</template>

<script>

// @ is an alias to /src


export default {
  name: 'Home',
  mounted(){
      this.texte();
  },
  methods:{
    coord:function(event){
      var croix = document.getElementById('mvmnt');
      var yh = event.clientY*100/window.innerHeight;
      var xl = event.clientX*100/window.innerWidth;
      var angley = (yh-50)/500;
      var anglex = (xl-50)/500;
      croix.style.transform="rotateX("+angley+"rad) rotateY("+anglex+"rad)";
        var curs = document.querySelector(".curs");
    var curs2 = document.querySelector(".curs2");
    curs2.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
    curs.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
    },
    openmenuhome:function(){
      var hb = document.querySelector('.hb');
      hb.classList.toggle('active-one');
      var nav = document.querySelector('nav');
      nav.classList.toggle('open');
      var backH = document.getElementById('backhome');
      backH.classList.toggle('backhomefront');
    },
    texte:function(){
        var nb_car = 67; 
        var tableau = ["H", "e", "y", " ", "!", "<br/>", "I", "'", "m", " ", "<span class=\"red\">L", "o", "u", "i", "s", " ", "C", "u", "e", "n", "o", "t</span>", ".", "<br/>", "F", "e", "e", "l", " ", "f", "r", "e", "e", " ", "t", "o", " ", "c", "o", "n", "t", "a", "c", "t", " ", "m", "e", " ", "!", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", ""]
        var texte = new Array;
        var txt = '';
        for (var i=0; i<nb_car; i++) {
            texte[i] = txt+tableau[i];
            txt = texte[i];
        }
        var actual_texte = 0;
        setInterval(function(){
            if(document.getElementById("text")){
            document.getElementById("text").innerHTML = texte[actual_texte];
            actual_texte++;
            if(actual_texte >= texte.length){
                actual_texte = 0;
            }
            }
        },150)
    }
  }
  
}
</script>

<style scoped>

    div#titreA>h1{
        margin-block: 0;
    }

  @media screen and (min-width:1000px) and (orientation:landscape){

      


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
        display: none;
    }

    .portrait{
        display: none;
    }

    .landscape{
        display: none;
    }



    /*S1 Laptop*/

        /*BG Home Laptop*/

                div#bghome{
                    width: 100%;
                    height: 100%;
                }


                svg#svghomelaptop{
                    position: absolute;
                    width: 100vw;
                    height: 100vh;
                }

                line#lignhomeonelaptop{
                    stroke-dasharray: 1500;
                    stroke-dashoffset: 1600;
                    animation: dash 2.5s ease forwards;
                }

                line#lignhometwolaptop{
                    stroke-dasharray: 1900;
                    stroke-dashoffset: 1600;
                    animation: dash 1.6s ease forwards;
                }

                line#lignhomethreelaptop{
                    stroke-dasharray: 1500;
                    stroke-dashoffset: 1600;
                    animation: dash 8s ease forwards;
                }
                
                @keyframes dash {
                    to{
                        stroke-dashoffset: 0;
                    }
                }

        /*Mvmnt Home*/

        div#mvmnt{
            position: absolute;
            width: 97vw;
            height: 97vh;
            z-index: 10;
            background-image: url(~@/assets/svghome.svg);
            background-size: 85%;
            background-repeat: no-repeat;
            background-position: center;
            pointer-events: none;
        }


        /*Contenu Home*/

                section#home{
                    width: 100%;
                    height: 100%;
                    display: grid;
                    grid-template-columns: 10.73vw 0.8vw 37.3vw 8.8vw 6.2vw 1fr;
                    grid-template-rows: 6.85vh 3.2vh 3.6vh 4.44vh 5.55vh 8vh 37.04vh 5vh 7.1vh 1fr;
                    opacity: 0;
                    animation: opac 3s ease forwards;
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

                section#home>a{
                    grid-row-start: 2;
                    grid-column-start: 6;
                    font-size: 2rem;
                    overflow:visible;
                    -webkit-text-stroke: 1px;
                    -webkit-text-stroke-color: #D2CECA;
                    color: transparent;
                    padding:0 10px;
                    border: #FF4655 solid 2px;
                    width: min-content;
                    height: min-content;
                    transition: 0.2s;
                    z-index: 2;
                }

                section#home>a:hover{
                    transform:scale(1.25);
                    color: #D2CECA;
                    background-color: #FF4655;
                }

                section#home nav{
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;
                    flex-wrap: wrap;
                    width:30vw;
                    height: 5vh;
                    grid-row-start: 4;
                    grid-column-start: 2;
                    font-size: 2vh;
                }

                section#home nav a{
                    z-index: 13;
                    transition: 0.5s;
                }

                section#home nav a:hover{
                    color: #FF4655;
                }


                section#home nav svg{
                    width: 65%;
                    transform: translateY(-4%);
                
                }

                section#home nav svg line{
                    stroke-dasharray: 30% 100% ;
                    stroke-dashoffset: 300%;
                    animation: navigation 1.5s ease forwards;
            
                }

                @keyframes navigation{
                    50%{
                        stroke-dasharray: 120%;
                        stroke-dashoffset: 0;
                    }
                    to{
                        stroke-dasharray: 30% 100% ;
                        stroke-dashoffset: 0;
                    }
                }
            


                section#home #titreA{
                    display: flex;
                    flex-direction: column;
                    width: min-content;                
                    grid-row-start: 7;
                    grid-column-start: 3;
                    overflow: visible;
                }

                section#home #titreA h1{
                    font-size: 8rem;
                    line-height: 7.5rem;
                    z-index: 1;
                    overflow: visible;
                }

                section#home #titreA svg{
                    transform: translateY(-15%);
                    overflow:visible;
                }

                section#home #titreA svg line{
                    stroke-dasharray: 1000;
                    stroke-dashoffset: 1100;
                    animation: dash 2s ease-in forwards;
                }


                section#home h2{
                    font-size: 1.91rem;
                    grid-row-start: 9;
                    grid-column-start: 2;
                    grid-column-end: 4;
                    align-self: center;
                }

                section#home #backhome{
                    font-size: 18rem;
                    -webkit-text-stroke: 5px;
                    -webkit-text-stroke-color: #345370;
                    color: transparent;
                    align-self: flex-end;
                    justify-self: end;
                    grid-row-start: 6;
                    grid-row-end: 8;
                    grid-column-start: 4;
                    grid-column-end: 7;
                    overflow: visible;
                }

                section#home #text{
                    width: max-content;
                    height: max-content;
                    grid-row-start: 8;
                    grid-column-start: 4;
                    font-size: 2vh;
                }

                

        
            }

@media screen and (orientation:portrait) {

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
        grid-column-start: 3;
        grid-row-start: 3;
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

          svg#svghomeportrait{
            position: absolute;
            width: 100vw;
            height: 100vh;
            left: 0;
            top: 0;
        }



        line#lignhomeoneportrait{
            stroke-dasharray: 200;
            stroke-dashoffset: 200;
            animation: dash 2s ease forwards;
        }

        line#lignhometwoportrait{
            stroke-dasharray: 150;
            stroke-dashoffset: 200;
            animation: dash 1.7s ease forwards;
        }

        line#lignhomethreeportrait{
            stroke-dasharray: 300;
            stroke-dashoffset: 300;
            animation: dash 2.3s ease forwards;
        }

        line#lignhomefourportrait{
            stroke-dasharray: 500;
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

          section#home{
              position: absolute;
              top: 0;
              left: 0;
              height: 100vh;
              width: 100vw;
              display: grid;
              grid-template-columns: 7.7vw 11.35vw 15vw 10.05vw 2.65vw 1fr;
              grid-template-rows: 5vh 9.65vh 19.84vh 26.77vh 12.5vh 1fr ;
              opacity: 0;
                animation: opac 3s ease forwards;
                transform: translateX(-10%);
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

          section#home>a{
                grid-column-start: 5;
                width: max-content;
                grid-row-start: 2;
                font-size: 2.2vh;
                overflow:visible;
                color: #D2CECA;
                padding:0 10px;
                background-color: #FF4655;
                height: min-content;
                z-index: 2;
          }

          section#home #titreA{
                grid-column-start: 2;
                grid-row-start: 4;
                height: max-content;
                width: min-content;
                font-size: 7vh;
                line-height: 11vh;
                display: flex;
                flex-direction: column;
                overflow: visible;
          }

          section#home #titreA svg{
              transform: translateY(-15%);
          }

          section#home #titreA h1{
              z-index: 1;
              margin: 0;
              margin-block-start: 0;
              margin-block-end: 0;
          }
          

          section#home #backhome{
                grid-column-start: 4;
                grid-row-start: 3;
                font-size: 18vh;
                height: max-content;
                width: max-content;
                -webkit-text-stroke: 4px;
                -webkit-text-stroke-color: #345370;
                color: transparent;
                z-index: -1;
          }

          section#home #backhome.backhomefront{
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

          section#home>h2{
                grid-column-start: 2;
                grid-row-start: 5;
                width: max-content;
                height: max-content;
                font-size: 2.7vh;
          }

          section#home #text{
                grid-column-start: 6;
                grid-row-start: 6;
                width: max-content;
                height: max-content;
          }    


          section#home nav{
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
          }

          section#home nav.open{
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

          section#home nav a{
              color:#1B2D3E;
              margin-bottom: 7vh;
              font-size: 3vh;
              z-index: 83;
          }

          section#home nav svg.laptop{
                display: none;
          }

          section#home nav.open svg.portrait{
              position: absolute;
              width: 100vw;
              height: 100vh;
              z-index: 82;
          }

          
   
}

@media screen and (max-width:999px) and (orientation:landscape){
    .hbrgr{
        top:50%;
        left:10%;
        width: 30px;
        height: 4px;
        background: #D2CECA;
        position: relative;
        box-shadow: 0 2px 5px rgba(0, 0, 0, .2);
        transition: 0.5s;
        overflow: visible;
      }
      
      .hbrgr:before {
        top: -16px;
        width: 40px;
      }
      
      .hbrgr:after {
        top: 16px;
        width: 20px;
      }

      .hb {
        width: 40px;
        height: 40px;
        cursor: pointer;
        overflow: visible;
        grid-column-start: 3;
        grid-row-start: 3;
        z-index: 100;
        grid-row-start: 2;
        grid-column-start: 3;
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
            width: 40px;
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
            width: 40px;
            background: #1B2D3E;
          }


          .laptop{
              display: none;
          }

          .portrait{
              display: none;
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

          section#home{
              width: 100vw;
              height: 100vh;
              display: grid;
              grid-template-columns: 4.3vw 9.5vw 34vw 4.2vw 5.98vw 1fr;
              grid-template-rows: 10.15vh 1.93vh 4.1vh 12.3vh 29.5vh 15vh 1fr;
              opacity: 0;
              animation: opac 3s ease forwards;
              transform: translateX(-10%);
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

          section#home>a{
            grid-column-start: 4;
            grid-row-start: 3;
            width: max-content;
            height: max-content;
            font-size: 3.4vh;
            overflow:visible;
            color: #D2CECA;
            padding:0 10px;
            background-color: #FF4655;
            z-index: 2;

          }

          section#home #titreA{
            grid-column-start: 2;
            grid-row-start: 5;
            width: min-content;
            height: max-content;
            font-size: 12vh;
            line-height: 19vh;
            display: flex;
            flex-direction: column;
            overflow: visible;
          }

          section#home #titreA svg{
              transform: translateY(-13%);
          }

          section#home #titreA h1{
            z-index: 1;
        }

          section#home h2{
            grid-column-start:2 ;
            grid-row-start:7;
            width: max-content;
            font-size:5vh ;
          }

          section#home #text{
            grid-column-start: 4;
            grid-row-start: 6;
            width: max-content;
            height: max-content;
          }    
          

          section#home #backhome{
              grid-column-start: 6;
              grid-row-start: 4;
              font-size: 35vh;
              width: max-content;
              height: max-content;
              -webkit-text-stroke: 4px;
              -webkit-text-stroke-color: #345370;
              color: transparent;
              z-index: -1;
          }

          section#home nav{
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
            z-index: 80;
            animation: navoff 600ms ease-out;
        }

        section#home nav.open{
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

      section#home nav a{
        color:#1B2D3E;
        margin-top: 7vh;
        font-size: 5vh;
        z-index: 81;
    }

    section#home #backhome.backhomefront{
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

    #svghomelandscape{
        position: absolute;
        width: 100vw;
        height: 100vh;
        top: 0;
        left: 0;
    } 


    line#lignhomeonelandscape{
        stroke-dasharray: 150;
        stroke-dashoffset: 150;
        animation: dash 2s ease forwards;
    }

    line#lignhometwolandscape{
        stroke-dasharray: 1100;
        stroke-dashoffset: 1100;
        animation: dash 1.8s ease forwards;
    }

    line#lignhomethreelandscape{
        stroke-dasharray: 100;
        stroke-dashoffset: 100;
        animation: dash 2s ease forwards;
    }

    line#lignhomefourlandscape{
        stroke-dasharray: 100;
        stroke-dashoffset: 100;
        animation: dash 2s ease forwards;
    }


    @keyframes dash {
        to{
            stroke-dashoffset: 0;
        }
    }

    section#home nav svg.landscape{
        position: absolute;
        width: 100vw;
        height: 100vh;
    }


}
</style>
