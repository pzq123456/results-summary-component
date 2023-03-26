<template>
    <div class="card-wrapper">
        <div class="card">
            <div class="card-left">

                <div class="title">
                    <h2>Your Result</h2>
                </div>

                <div class="circle">
                    <h1>76</h1>
                    <p>of 100</p>
                </div>
                <div class="commit">
                    <h2>Great</h2>
                    <p>
                        You scored higher than 65% of the people who have taken these tests.
                    </p>
                </div>




            </div>
            <div class="card-right">
                <h2>Summary</h2>
                <div v-for=" (data, index ) in dataList" :key="data.category" class="dataBar" :style="colors[index]">
                    <!-- img with path of data.icon -->
                    <div class="icon" >
                        <img :src=data.icon alt="icon">
                    </div>
                    <h3 :style="TextColors[index]">{{data.category}}</h3>
                    <div class="score-end">
                        <span class="strong">{{data.score}}</span>
                        <span class="weak">/ 100</span>
                    </div>

                </div>
                <button>Continue</button>
            </div>
        </div>

    </div>
</template>

<script setup>
import { ref } from 'vue'
// https://pzq123456.github.io/results-summary-component/images/icon-reaction.svg
const dataList = ref([
  {
    "category": "Reaction",
    "score": 80,
    "icon": "https://pzq123456.github.io/results-summary-component/images/icon-reaction.svg",
  },
  {
    "category": "Memory",
    "score": 92,
    "icon": "https://pzq123456.github.io/results-summary-component/images/icon-memory.svg"
  },
  {
    "category": "Verbal",
    "score": 61,
    "icon": "https://pzq123456.github.io/results-summary-component/images/icon-verbal.svg"
  },
  {
    "category": "Visual",
    "score": 72,
    "icon": "https://pzq123456.github.io/results-summary-component/images/icon-visual.svg"
  }
]);
        // --primary-light-red: hsl(0, 100%, 67%);
        // --primary-orangey-yellow: hsl(39, 100%, 56%);
        // --primary-green-teal: hsl(166, 100%, 37%);
        // --primary-cobalt-blue: hsl(234, 85%, 45%);
const colors = ref([
    `background-color:hsl(0, 100%, 67%, 0.05)`,
    `background-color:hsl(39, 100%, 56%, 0.05)`,
    `background-color:hsl(166, 100%, 37%, 0.05)`,
    `background-color:hsl(234, 85%, 45%, 0.05)`
]);

const TextColors = ref([
    `color:hsl(0, 100%, 67%)`,
    `color:hsl(39, 100%, 56%)`,
    `color:hsl(166, 100%, 37%)`,
    `color:hsl(234, 85%, 45%)`
]);

</script>

<style scoped>
    .card-wrapper{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .card{
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        max-width: 740px;
        height: 520px;
        background-color: var(--neutral-white);
        border-radius: 30px;
        box-shadow: 0px 0px 30px 0px rgba(50, 78, 238, 0.308);
    }
/* left card */
    .card-left{
        width: 50%;
        height: 100%;

        /* vertical gradient bacground  var(--gradient-light-slate-blue) var(--gradient-light-royal-blue) */
        background: linear-gradient(180deg, var(--gradient-light-slate-blue) 0%, var(--gradient-light-royal-blue) 100%);
        border-radius: 30px;


        /* flex */
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: start;


    }

    .card-right{
        width: 50%;
        height: 100%;
        border-radius: 0 20px 20px 0;

        /* flex */
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: start;

    }

    .card-left h2{
        color: var(--neutral-white);
        font-size: 24px;
        font-weight: 700;
        margin: 20px 0 0 20px;
    }

    .card-left h1{
        color: var(--neutral-white);
        font-size: 120px;
        font-weight: 700;
        margin: 20px 0 0 20px;
    }

    .card-left h3{
        color: var(--neutral-white);
        font-size: 24px;
        font-weight: 700;
        margin: 0 0 0 20px;
    }
    .card-right h2{
        color: var(--neutral-dark-blue);
        font-size: 24px;
        font-weight: 700;
        margin: 20px 0 0 40px;
    }

    .dataBar{
        width:100%;
        height: 60px;
        display: flex;
        align-items: center;
        margin: 0 auto;
        border-radius: 10px;
    }

    .dataBar h3{
        color: var(--neutral-dark-blue);
        font-size: 18px;
        font-weight: 700;
        margin: 0 0 0 20px;
    }

    .dataBar span{
        /* color: var(--neutral-dark-blue); */
        font-size: 18px;
        font-weight: 400;
        margin: 0 0 0 20px;
    }   

    .dataBar .icon{
        width: 40px;
        height: 40px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .dataBar .icon img{
        width: 20px;
        height: 20px;
    }

    .card-right button{
        width: 300px;
        height: 55px;

        background-color: var(--neutral-dark-gray-blue);
        border-radius: 50px;
        border: none;
        color: var(--neutral-white);
        font-size: 18px;
        font-weight: 700;
        margin-bottom: 40px;
        margin-left: 40px;
    }

    .card-right button:hover{
        background-color: var(--gradient-light-royal-blue);
    }

    /* align in right */
    .score-end{
        display: flex;
        justify-content: flex-end;
        align-items: center;
        width: 100%;
        height: 100px;
        margin: 0 40px 0 0;
    }

    .score-end .strong{
        font-weight: 700;

    }

    .score-end .weak{
        font-weight: 600;
        color:rgba(11, 11, 11, 0.413);
    }


    .title{

        /* background-color: rgba(240, 248, 255, 0.471);  */
        /* center */
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        
    }

    .title h2{

        font-size: 24px;
        font-weight: 700;
        color:var(--neutral-light-lavender)
    }

    .circle{
        width: 180px;
        height: 180px;
        /* background-color: rgba(240, 248, 255, 0.609); */
        border-radius: 50%;

        /* align elemnts center and clumn*/
        display: flex; 
        justify-content: center;
        align-items: center;
        flex-direction: column;

        /* center itself */
        margin: 0 auto;

        /* gradient background-color inverse against the left card */
        background: linear-gradient(180deg, 
        var(--gradient-violet-blue) 0%, 
        var(--gradient-persian-blue) 100%);


    }

    .circle h1{
        font-size: 80px;
        font-weight: 600;
        color:var(--neutral-white);
    }

    .circle p{
        font-size: 16px;
        font-weight: 600;
        color:rgba(244, 242, 246, 0.365);
    }

    .commit{
        width: 300px;
        height: 150px;
        /* background-color: rgba(240, 248, 255, 0.609); */

        /* align elemnts center and clumn*/
        display: flex; 
        /* justify-content: center;
        align-items: center; */
        flex-direction: column;

        /* center itself and up from the buttom*/
        margin: 0 auto;
        margin-bottom: 40px;

        /* space betweent items */
        gap: 20px;
    }

    .commit h2{
        font-size: 32px;
        font-weight: 600;
        color:var(--neutral-white);
        /*self cneter */
        margin: 0 auto;

    }

    .commit p{
        /* font-size: 18px;
        font-weight: 400;
        color:var(--neutral-light-lavender);
        margin-bottom: 60px;

        text-align:start; */

        /* space between characters */
        letter-spacing: 1px;

        font-size: 0.75rem;
        width: 200px;
        font-weight: 600;
        color: var(--neutral-light-lavender);

        line-height: 1.5;
        text-align: center;
        /* background-color: rgba(240, 248, 255, 0.539); */

        /*align self center */
        margin: 0 auto;
    }


    @media screen and (max-width: 375px) {
        .card{ 
            /* aligin items in column */
            flex-direction: column;

            /* center */
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;

            /* center itself */
            margin: 0 auto;

            height: 100%;
            width: 100%;
        }

        .card-left{
            /* center */
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;

            /* center itself */
            margin: 0 auto;

            height: 100%;
            width: 100%;


        }

        .card-right{
            height: 100%;
            width: 100%;
            /* center */
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;


            /* center itself */
            margin: 0 auto;
        }

        
    }


</style>