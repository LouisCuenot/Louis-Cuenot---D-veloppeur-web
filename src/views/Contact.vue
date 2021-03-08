<template>
    <div class="body" v-on:mousemove="coord">
        <div class="bgcontact"></div>
        <div id="midline"></div>
        <div class="card">
            <form class="contact-form" @submit.prevent="sendEmail">   
                <ul>
                    <li v-on:click="checkhi">
                        <input type="checkbox" name="hi" id="checkboxhi" checked>
                        <label for="checkboxhi" class="montserratM">Hi !</label>
                    </li>
                    <li v-on:click="checkjob">
                        <input type="checkbox" name="job" id="checkboxjob">
                        <label for="checkboxjob" class="montserratM">Have a job offer ?</label>
                    </li>
                </ul>
                <input class="montserratM" type="email" name="user_mail" id="mail" placeholder="Email" required>
                <div>
                    <input type="text" name="user_name" class="montserratM" placeholder="Name" required>
                    <input type="text" name="user_firstname" class="montserratM" placeholder="First Name" required>
                </div>
                <textarea name="message" id="msg" class="montserratM" placeholder="Message ..." required></textarea>
                <input type="submit" value="Send" class="staatliches">
            </form>
            <div class="sendok">
                <p class="montserratM">Votre message a bien été envoyé !</p>
                <div class="checkmark"></div>
                
            </div>
            
            <div id="divpp">
                <img src="@/assets/pp.png">
            </div>
        </div>
        
        <p id="contactme" class="anton">Contact me !</p>
        <nav>
            <router-link class="montserratM white" to="/">Home</router-link>
            <router-link class="montserratM white" to="/projects">Projects</router-link>
            <router-link class="montserratM white" to="/about">About</router-link>
        </nav>
    </div>
</template>

<script>
import emailjs from 'emailjs-com';
export default {
    name: 'Contact',
    methods:{
        coord:function(event){
            var yh = event.clientY*100/window.innerHeight;
            var xl = event.clientX*100/window.innerWidth;
            var curs = document.querySelector(".curs");
            var curs2 = document.querySelector(".curs2");
            curs2.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
            curs.style.cssText = "left:"+xl+"%; top:"+yh+"%;";
    },
        sendEmail: (e) => {
      emailjs.sendForm('service_qu1izie', 'template_wb2xv54', e.target, 'user_RalYErrUvSBsU7U464Tf2')
        .then((result) => {
            console.log('SUCCESS!', result.status, result.text);
            var card = document.querySelector('.card');
            card.classList.add('sended');
        }, (error) => {
            console.log('FAILED...', error);
            window.alert("An error has occured, please try later.");
        });
    },
    checkhi:function(){
        var checkhi = document.getElementById('checkboxhi');
        var checkjob = document.getElementById('checkboxjob');
        if(checkhi.checked===true){
            checkjob.checked=false;
        }else{
            checkjob.checked=true;
        }
        
        
    },
    checkjob:function(){
        var checkhi = document.getElementById('checkboxhi');
        var checkjob = document.getElementById('checkboxjob');
        if(checkjob.checked===true){
            checkhi.checked=false;
        }else{
            checkhi.checked=true;
        }
        
        
    }
}
}
</script>

<style scoped>



.card>.sendok>p.montserratM{
    width: 0;
    overflow: hidden;
    border: #FF4655 solid 0px;
}

form>ul{
    list-style: none;
    padding: 0;
    margin: 0;
}

p#contactme{
    padding: 0;
    margin: 0;
}

@media  screen and (orientation:landscape) {
    


    .body{
        width: 100vw;
        height: 100vh;
        background-image: url(~@/assets/bg.png);
        background-size:  auto 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }

    .bgcontact{
        height: 130vh;
        width: 50vw;
        background-image: url(~@/assets/bgw.png);
        background-size:  auto 100%;
        position: absolute;
        right: -10vw;
        top: -10vh;
        transform: rotate(10deg);
    }

    .card{
       
        background: radial-gradient(ellipse at center, #ffffff 0%, #f6f6f6 47%, #ededed 100%);
        width: 60vw;
        height: 80vh;
        border-radius: 40px;
        padding: 0 5vw;
        box-sizing: border-box;
        box-shadow: 6px 6px 58px 3px rgba(0,0,0,0.51);
        z-index: 1;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    form{
        width: 40%;
        height: 60%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;
        transition: 0.5s;
    }

    .sended form{
        animation: sendedform 5s ease forwards;
    }

    @keyframes sendedform {
        20%{
            transform: translateX(6vw);
            width: 30%;
            opacity: 1;
        }
        50%{
            width: 0;
            opacity: 0;
            transform: translateX(24.5vw);
        }
        100%{
            width: 0;
            transform: translateX(24.5vw);
        }

        
    }

    form ul{
        display: flex;
        justify-content: space-between;
        width: 100%;
        height: max-content;
    }

    form li{
        width: 50%;
       
    }

     form li label{
        padding-left: 6px;
        color: #0d3a5f;
        font-weight: bold;
    }

    form>input:first-of-type{
        height: 15%;
        width: 100%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
                inset -7px -7px 12px #ffffff;
        padding-left: 20px;
        box-sizing: border-box;
        background-color: transparent;
    }


    form>div{
        display: flex;
        justify-content: space-between;
        height: 15%;
        width: 100%;
    }  



    form>div>input{
        
        background-color: transparent;
        height: 100%;
        width: 48%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
            inset -7px -7px 12px #ffffff;  
        padding-left: 20px;
        box-sizing: border-box; 
        
        }


    textarea{
        width: 100%;
        height: 30%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
            inset -7px -7px 12px #ffffff;
        background-color: transparent;
        resize: none;
        padding-left: 15px;
        padding-top:15px;
        box-sizing: border-box;
    }

    form>input:last-of-type{
        width: 100%;
        border: 2px #FF4655 solid;
        height: 15%;
        background-color: transparent;
        letter-spacing: 1px;
        transition:0.5s;
        color: #0d3a5f;
    }

    form>input:last-of-type:hover{
        background-color: #FF4655;
        color: #ffffff;
    }

    form *{
        outline: none;
    }

    #divpp{
        width: 40%;
        height: 20vw;
        overflow: visible;
        border: #FF4655 5px solid;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: center;
        transition: 0.5s;
    }


    .sended #divpp{
        animation: sendeddivimg 5s ease forwards;
    }

    @keyframes sendeddivimg {
        20%{
            transform: translateX(-4.5vw);
            width: 20vw;
            height: 20vw;
        }
        50%{
            width: 0;
            height: 0;
            transform: translateX(-24.5vw);
            border: #FF4655 1px solid;
        }
        65%{
            transform: translateX(-27vw);
            width: 0;
            height: 0;
            border: #FF4655 1px solid;
        }
        80%{
            transform: translateX(-27vw);
            width: 20vw;
            height: 20vw;
            border: #FF4655 5px solid;
        }
        100%{
            transform: translateX(-30vw);
        }

        
    }

    #divpp img{
        margin-top: -2.653vw;
        width: 80%;
        z-index: 2;
    }

    

    #midline{
        width: 2px;
        opacity: 0.4;
        height: 64%;
        background-color: #FF4655;
        position: absolute;
        left: 50%;
        z-index: 4;
        transform: translateX(-6px);
    }


    .card>.sendok{
        width: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        height: 25%;
    }

    .card>.sendok>p{
        padding:  5% 2%;
        text-align: center;
        font-size: 13px;
        font-weight: 600;
        border: #FF4655 2px solid;
    }

    .sendok>div{
        width:0;
        height:0;
        background-image: url(~@/assets/checkmark.svg);
    }

    .sended>.sendok{
        animation: sendedp 5s ease forwards;
    }

    .sended>.sendok>div{
        animation: sendcheck 5s ease forwards;
    }

    @keyframes sendcheck {
        80%{
            width: 0;
            height: 0;
        }
        92%{
            width:7vh;
            height:7vh;
        }
        100%{
            width:5vh;
            height:5vh;
        }
    }

    @keyframes sendedp {
        50%{
            padding:  0;
            width: 0;   
            transform: translateX(4vw); 
            
        }

        80%{
            transform: translateX(24vw);
            width: 20vw;
            
        }

        100%{
            transform: translateX(24vw);
            width: 20vw;
        }
    }

    #contactme{
        width: max-content;
        position: absolute;
        z-index: 3;
        left:25vw;
        top: 18vh;
        transform: translateY(-50%);
        font-size: 2vw;
        text-transform: uppercase;
        text-orientation: upright;
        border-bottom: 2px solid #FF4655;
        color: #0d3a5f;
    }


    nav{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        position: absolute;
        left: 5vw;
        width: 15vw;
        height: 25vh;
        top: 50%;
        transform: translateY(-50%);
    }

    nav>a{
        font-size: 2.5vh;
        transition: 0.5s;
        width: max-content;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    nav>a:hover{
        color: #FF4655;
        transform: translateX(20px);
        font-size: 3vh;
        border-bottom: 2px solid #D2CECA;
    }

    

}

@media  screen and (orientation:landscape) and (max-width: 999px) {
    form input{
        font-size: 8px;
    }

    textarea{
        font-size: 8px;
    }

    form>input:last-of-type{
        font-size: 11px;
    }

    form label{
        font-size: 8px;
    }
}

@media  screen and (orientation:landscape) and (min-width: 1000px) {
    form>input:last-of-type{
        font-size: 16px;
    }

    textarea{
        font-size: 12px;
    }

    form input{
        font-size: 12px;
    }

    form label{
        font-size: 12px;
    }

}

@media screen and (orientation:portrait) {
    .body{
        width: 100vw;
        height: 100vh;
        background-image: url(~@/assets/bg.png);
        background-size:  auto 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }

    .bgcontact{
        height: 50vh;
        width: 130vw;
        background-image: url(~@/assets/bgw.png);
        background-size:  auto 100%;
        position: absolute;
        bottom: -10vh;
        left: -10vw;
        transform: rotate(10deg);
    }

    .card{
        background: radial-gradient(ellipse at center, #ffffff 0%, #f6f6f6 47%, #ededed 100%);
        width: 80vw;
        height: 80vh;
        border-radius: 40px;
        padding: 5vh 0;
        box-sizing: border-box;
        box-shadow: 6px 6px 58px 3px rgba(0,0,0,0.51);
        z-index: 1;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }

    #midline{
        height: 2px;
        opacity: 0.4;
        width: 50vw;
        background-color: #FF4655;
        position: absolute;
        top: 50%;
        left: 50%;
        z-index: 4;
        transform: translateX(-50%);
    }

    nav{
        display: flex;
    
        justify-content: space-between;
        position: absolute;
        left: 10vw;
        width: 80vw;
        height: 7vh;
        top: 3vh;
    }

    nav>a{
        font-size: 2vh;
        transition: 0.5s;
        width: max-content;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    form{
        width: 80%;
        height: 40%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        transition: 0.5s;
    }

    .sended form{
        animation: sendedform 5s ease forwards;
    }

    @keyframes sendedform {
        20%{
            transform: translateY(6vh);
            height: 40%;
            opacity: 1;
        }
        50%{
            height: 0;
            opacity: 0;
            transform: translateY(20vh);
        }
        100%{
            height: 0;
            transform: translateY(20vh);
        }

        
    }



    form ul{
        display: flex;
        justify-content: space-between;
        width: 100%;
        height: max-content;
    }

    form li{
        width: 50%;
       
    }

     form li label{
        padding-left: 6px;
        color: #0d3a5f;
        font-weight: bold;
        font-size: 12px;
    }

    form>input:first-of-type{
        height: 15%;
        width: 100%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
                inset -7px -7px 12px #ffffff;
        padding-left: 20px;
        box-sizing: border-box;
        background-color: transparent;
        font-size: 10px;
    }


    form>div{
        display: flex;
        justify-content: space-between;
        height: 15%;
        width: 100%;
    }  



    form>div>input{
        
        background-color: transparent;
        height: 100%;
        width: 48%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
            inset -7px -7px 12px #ffffff;  
        padding-left: 20px;
        box-sizing: border-box; 
        font-size: 10px;
        
        }


    textarea{
        width: 100%;
        height: 30%;
        border: none;
        box-shadow: inset 7px 7px 12px #bcbcbc,
            inset -7px -7px 12px #ffffff;
        background-color: transparent;
        resize: none;
        padding-left: 15px;
        padding-top:15px;
        box-sizing: border-box;
        font-size: 10px;
    }

    form>input:last-of-type{
        width: 100%;
        height: 15%;
        letter-spacing: 1px;
        transition:0.5s;
        background-color: #FF4655;
        border: 2px #FF4655 solid;
        color: #ffffff;
    }


    form *{
        outline: none;
    }

    #divpp{
        width: 27vh;
        height: 27vh;
        overflow: visible;
        border: #FF4655 5px solid;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: center;
        transition: 0.5s;
    }

    #divpp img{
        margin-top: -3.582vh;
        width: 80%;
        z-index: 2;
    }

    .sended #divpp{
        animation: sendeddivimg 5s ease forwards;
    }

    @keyframes sendeddivimg {
        20%{
            transform: translateY(-4.5vh);
            width: 27vh;
            height: 27vh;
        }
        50%{
            width: 0;
            height: 0;
            transform: translateY(-31.5vh);
            border: #FF4655 1px solid;
        }
        65%{
            transform: translateY(-35vh);
            width: 0;
            height: 0;
            border: #FF4655 1px solid;
        }
        80%{
            transform: translateY(-35vh);
            width: 27vh;
            height: 27vh;
            border: #FF4655 5px solid;
        }
        100%{
            transform: translateY(-39vh);
        }

        
    }

    .card>.sendok{
        height: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        width: 60%;
    }

    .card>.sendok>p{
        padding:  5% 2%;
        text-align: center;
        font-size: 13px;
        font-weight: 600;
        border: #FF4655 2px solid;
    }

    .sendok>div{
        width:0;
        height:0;
        background-image: url(~@/assets/checkmark.svg);
        background-position: center;
        background-repeat: no-repeat;
    }

    .sended>.sendok{
        animation: sendedp 5s ease forwards;
    }

    .sended>.sendok>div{
        animation: sendcheck 5s ease forwards;
    }

    @keyframes sendcheck {
        80%{
            width: 0;
            height: 0;
        }
        92%{
            width:7vh;
            height:7vh;
        }
        100%{
            width:5vh;
            height:5vh;
        }
    }

    @keyframes sendedp {
        50%{
            padding:  0;
            height: 0;   
            transform: translateY(4vh); 
            
        }

        80%{
            transform: translateY(33vh);
            height: 20vh;
            
        }

        100%{
            transform: translateY(33vh);
            height: 20vh;
        }
    }

    #contactme{
        display: none;
    }


}


</style>