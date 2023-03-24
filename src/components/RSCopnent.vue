<template>
   <div class="wrapper">
    <div class="contentLeft">
        <h2>Your Result</h2>
        <div class="circle">
            <div class="context">
                <h1 class="score">
                    76
                </h1>
                <p class="scorel">
                    of 100
                </p>
            </div>

        </div>
    </div>
    <div class="contentRight">
        <h2>Right</h2>
    </div>
   </div>
</template>

<script setup>

</script>

<style scoped>
.wrapper{
    /* 
    desktop: 1440px
    mobile: 375px
    fit the mobile first
    center the content
    */
    max-width: 740px;
    height: 480px;
    margin: 0 auto;

    place-items: center;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    grid-template-areas: "contentLeft contentRight";
    margin-top: 250px;

    box-shadow: 0px 0px 30px 0px rgba(8, 33, 220, 0.213);
    border-radius: 30px;




}

.contentLeft{
    /* horizontal gradient */
    background: linear-gradient(
        180deg,
        var(--gradient-light-slate-blue) 0%,
        var(--gradient-light-royal-blue) 100%
    );

    width: 100%;
    height: 100%;
    display: grid;
    place-items: center;

    /* radius */
    border-radius: 30px;
}

.contentRight{
    background-color: var(--neutral-white);
    width: 100%;
    height: 100%;
    display: grid;
    place-items: center;

    /* border-radius: 30px; */
    /* radius only in right part */
    border-radius: 30px;

    /* shadow in right edge and button edge */

}

.circle{
    width: 200px;
    height: 200px;

    background: linear-gradient(
        180deg,
        var(--gradient-violet-blue) 0%,
        var(--gradient-persian-blue) 100%
    );

    border-radius: 50%;
    display: grid;
    place-items: center;
    margin-bottom: 140px;

   
}

.score{
    font-size: 90px;
    font-weight: 700;
    color: var(--neutral-white);
}

p{
    font-size: 18px;
    font-weight: 700;
    color: var(--neutral-light-lavender);
}

.scorel{
    font-size: 18px;
    font-weight: 700;
    color: hsla(241, 100%, 89%, 0.607);
}
.context{
    display: grid;
    place-items: center;
}

h2{
    font-size: 25px;
    font-weight: 600;
    color: var(--neutral-light-lavender);
    margin-bottom: 20px;
}

</style>