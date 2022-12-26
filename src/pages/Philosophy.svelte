<script>
    import Banner from './components/Philosophy/Banner.svelte';
    import Style from './components/Philosophy/Style.svelte';

    
    let step = 1, max = 2

    function next() {
        if(step < max) { step++; return }
        if(step = max) { step = 1; return }
    }

    function prev() {
        if(step == 1) { step = max; return }
        if(step <= max) { step--; return }
    }


</script>

<div class="container">
    <div class="navbtn left" on:click={next} on:keypress={next}></div>
    <div class="navbtn right" on:click={prev} on:keypress={prev}></div>
    {#if step == 1}
        <Style/>
    {/if}
    {#if step == 2}
        <Banner/>
    {/if}
    
</div>

<style>
    .navbtn {
        width: 5vw;
        height: 100%;
        position: absolute;
        top: 0px;
        transition: .5s;
        cursor: pointer;
    }

    .navbtn:hover {
        opacity: .5;
        transition: .5s;
        background-color: rgba(0, 0, 0, 0.1);
    }

    .navbtn.left {
        left: 0px;
    }

    .navbtn.right {
        right: 0px;
    }

    .navbtn.left::after {
        content: '❮';
        font-size: 3vw;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        margin: 0px;
        opacity: .5;
        max-height: 30px;
    }

    .navbtn.right::after {
        content: '❯';
        font-size: 3vw;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        margin: 0px;
        opacity: .5;
        max-height: 30px;
    }

    .container {
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
    }
    

    @media screen and (max-width: 750px) {
        .navbtn {
            width: 10vw;
        }
    }
    @media screen and (max-width: 300px) {
        .navbtn {
            width: 15vw;
        }
    }
</style>