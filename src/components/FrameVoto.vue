<template>
  <div class="box">
    
        <div v-if="show" class="content_one">
            <div class="firstly">¿QUE TE HA PARECIDO EL CURSO?</div>
            <p class="opinion">Nos importa mucho tu opinion para seguir mejorando el contenido y experiencia de la plataforma.</p>
            <div class="ranking">
                <div :class="item.list_class" v-for="(item, index) in items" :key="item.id" @click="sending_opinion(index)">{{ item.list_name }}</div>
            </div>
            <div class="rect">
                <button class="sending" type="button" @click="show=!show;hide=!hide">Enviar respuesta</button>
            </div>
        </div>
    
    <transition name="fade">
        <div v-if="hide" class="content_two">
            <img class="message" src="../assets/opinion.jpg" alt="opinion">
            <div class="firstly">Gracias por tu Apoyo</div>
            <p class="opinion">Trabajemos en conjunto para mejorar cada dia gracias a tu apoyo.</p>
        </div>
    </transition>
  </div>
</template>
<script>
export default {
    data() {
        return{
            show:true,
            hide:false,
            items: [
                {list_name:1,list_class:"button_one"},
                {list_name:2,list_class:"button_one"},
                {list_name:3,list_class:"button_one"},
                {list_name:4,list_class:"button_one"},
                {list_name:5,list_class:"button_one"}
            ]
        };
    },
    methods: {
        sending_opinion(index){
            this.items[index].list_class="button_two";
        },
    }
};
</script>
<style scoped>
.message{
    width: 100%;
}
.box{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
.content_one{
    background-color: white;
    width:400px;
    margin: 0px;
    padding: 25px;
    border: 5px solid black;
    border-radius: 15px;
}
.content_two{
    background-color: white;
    width:400px;
    margin: 0px;
    padding: 25px;
    border: 5px solid black;
    border-radius: 15px;
}
.firstly{
    font-weight: 900;
    color: black;
    font-size: 30px;
    font-family: Arial, Helvetica, sans-serif;
}
.opinion{
    color: black;
    font-size: 18px;
    line-height: 1.5;
    font-family: Arial, Helvetica, sans-serif;
}
.ranking{
    display: flex;
    justify-content: center;
}
.button_one{
    width:30px;
    height:30px;
    border: 3px solid black;
    border-radius: 100px;
    padding: 10px;
    margin-right: 15px;
    font-size: 22px;
    font-weight: 900;
    text-align: center;
    transition: 0.5s;
    cursor: pointer;
}
.button_two{
    background-color: #0F172D;
    color: white;
    width:30px;
    height:30px;
    border: 3px solid #0F172D;
    border-radius: 100px;
    padding: 10px;
    margin-right: 15px;
    font-size: 22px;
    font-weight: 900;
    text-align: center;
    transition: 0.5s;
    cursor: pointer;
}
.button_one:hover{
    width:30px;
    height:30px;
    color: white;
    background-color: #8E74B9;
    border: 3px solid black;
    border-radius: 100px;
    padding: 10px;
    margin-right: 15px;
    font-size: 22px;
    font-weight: 900;
    text-align: center;
}
.rect{
    text-align: center;
    margin-top: 30px;
}
.sending{
    width: 350px;
    background-color: #0F172D;
    color: white;
    border-radius: 30px;
    font-weight: 600;
    font-size: 16px;
    font-family: Arial, Helvetica, sans-serif;
    padding: 10px;
    transition: 0.5s;
}
.sending:hover{
    width: 350px;
    background-color: #A578E1;
    color: #0F172D;
    border-radius: 30px;
    font-weight: 600;
    font-size: 16px;
    font-family: Arial, Helvetica, sans-serif;
    padding: 10px;
}
</style>