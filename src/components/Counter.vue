<template>
  <h2>{{customTitle}}</h2>
  <p>{{counter}} <sup>2</sup> = {{squareCounter}} </p>

  <div>
    <button @click="increase()"> + </button>
    <button @click="decrease()"> - </button>
  </div>
</template>

<script>
export default {
    props:{
        title:String,
        start:{
            type:Number,
            default:10,
            validator(value){
                return value > 1
            }
        }
    },
    data(){
        return{
            counter:this.start
        }
    },
    methods:{
        increase(){
            this.counter++;
        },
        decrease(){
            this.counter--;
        }
    },
    computed:{
        squareCounter(){
            return this.counter * this.counter
        },
        customTitle(){
            return this.title || 'Default'
        }

    }
}
</script>

<style>
    button{
        background: #64B687;
        border-radius: 5px;
        border: 1px solid white;
        color: white;
        cursor: pointer;
        margin:0 5px;
        padding: 5px 15px;
        transition: 0.3s ease-in-out;
    }

    button:hover{
        background: #5aa67b;
        transition: 0.3s;
    }
</style>