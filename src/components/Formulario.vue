<template>
    <div class="wrapper container">
        <div class="wrapper__left">
            <div class="wrapper__form">
                <div class="formDiv" id="startForm">
                    <label for="background">Color de fondo</label>
                    <input placeholder="darkgreen" v-model="fondo"/>
                </div>
                <div class="formDiv">
                    <label for="color">Color de texto</label>
                    <input placeholder="red" v-model="color"/>
                </div> 
                <div class="formDiv2">
                    <label for="showText">Mostrar texto</label>
                    <input style="margin-left: 10px;" type="checkbox" name="showText" id="showText" v-model="mostrar">
                </div>
                <div class="formDiv">
                    <label for="border">Borde</label>
                    <input type="range" name="borde" id="border" min="0" max="100" v-model="borde">
                </div>
                <div class="formDiv">
                    <label for="textContent">Contenido Textual</label>
                    <textarea name="content" id="textContent" placeholder="Awesome VUE.js" v-model="contenido"></textarea>
                </div>
                <div class="formDiv">
                    <label for="fFamily">Tipografía</label>
                    <input type="text" placeholder="italic" v-model="estilo"/>
                </div>
                <div class="formDiv2">
                    <label for="opas">Opaco</label>
                    <input style="margin-left: 10px;" type="checkbox" name="opaco" id="opaco" v-model="opaco">
                </div>
                <div class="formDiv" id="endForm">
                    <label for="sizeF">Tamaño de letra</label>
                    <div>
                        <input value="small" type="radio" name="sizeF" id="small" v-model="tamano" class="m-1">
                        <label for="small" class="m-1">pequeño</label>
                        <input value="medium"type="radio" name="sizeF" id="medium" v-model="tamano" class="m-1">
                        <label for="medium" class="m-1">mediano</label>
                        <input value="large" type="radio" name="sizeF" id="large" v-model="tamano" class="m-1">
                        <label for="large" class="m-1">grande</label>
                    </div>
                </div>
            </div>
        </div>
        <div class="wrapper__right">
            <div class="wrapper__right--box" :class="{opacity: opaco}"
            :style="{
                backgroundColor: fondo,
                borderRadius: borde+'%',
                }">
                    <p :class="{mostrar: !mostrar}" id="text" :style="{
                        color: color,
                        fontStyle: estilo,
                        fontSize: tamano,
                    }">
                        {{contenido}}
                    </p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "formulario",
    data(){
        return{
            fondo: "",
            color: "",
            mostrar: false,
            borde: 0,
            contenido: "",
            estilo: "",
            opaco: false,
            tamano: ""
        }
    }
}
</script>
<style scoped>
    .mostrar{
        display: none;
    }
    .opacity{
        opacity: 0.5;
    }
    .wrapper{
        height:500px;
        width: 100%;
    }
    .wrapper__left{
        height: 100%;
        width: 50%;
        border: 1px solid black;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .wrapper__right{
        height: 100%;
        width: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        border: 1px black solid;
    }
    .wrapper__right--box{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 300px;
        height: 300px;
    }
    .wrapper{
        display: flex;
        flex-direction: row;
    }
    .wrapper__form{
        height: 80%;
        width: 40%;
        background-color: darkslategray;
        color: white;
    }
    label{
        text-align: start;
    }
    /* label, input, textarea{
        margin: 10px;
    } */
    input, textarea{
        margin: 5px 0;
    }
    .formDiv{
        display: flex;
        flex-direction: column;
    }
    .formDiv2{
        display: flex;
        justify-content: start;
    }
    .formDiv, .formDiv2{
        margin: 0 20px;
    }
    #startForm{
        margin: 30px 20px 0 20px;
    }
    .opaco{
        opacity: 20;
    }
</style>