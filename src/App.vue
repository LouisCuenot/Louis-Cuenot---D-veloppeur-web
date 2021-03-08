<template>
  <router-view/>
  <div class="curs laptop"></div>
  <div class="curs2 laptop"></div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Anton&family=Kanit:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Staatliches&display=swap');

body{

    padding: 0;
    margin: 0;
    overflow: hidden;
    user-select: none;
    cursor: none;

}


a{
    color:#000000;
    text-decoration: none;
}

/*Fonts*/

.kanitEL{
    font-family: "Kanit ExtraLight",sans-serif;
}

.kanitT{
    font-family: "Kanit Thin",sans-serif;
}

.montserratM{
    font-family: "Montserrat Medium",sans-serif;
}

.staatliches{
    font-family: Staatliches,sans-serif;
}

.anton{
    font-family: Anton,sans-serif;
}

.uppercase{
    text-transform: uppercase;
}

                /* Fin des Fonts */

/* Couleurs */

.red{
    color: #FF4655;
}

.blue{
    color: #4B9FF0;
}

.green{
    color: #389A31;
}

.white{
    color: #D2CECA;
}

                /* Fin des couleurs*/

 .zi{
                    z-index: 12;
}

.curs2{
    position: fixed;
    width: 4px;
    height: 4px;
    background-color:#111111;
    border-radius: 50%;
    left: 0;
    top: 0;
    pointer-events: none;
    transform: translate(-50%, -50%); z-index: 999;
}

.curs{
    position: fixed;
    width: 26px;
    height: 26px;
    border: 2px solid #FFD700;
    border-radius: 42%;
    left: 0;
    top: 0;
    pointer-events: none;
    transform: translate(-50%, -50%);
    transition: .900ms;
    z-index: 999;
}

@media screen and (orientation:portrait) {
    .laptop{
              display: none;
          }
}

@media screen and (max-width:999px) and (orientation:landscape){
    .laptop{
              display: none;
          }
}

   
</style>
