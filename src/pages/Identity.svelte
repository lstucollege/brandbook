<script>
    import BwLogo from "./components/Identity/BwLogo.svelte";
    import Colors from "./components/Identity/Colors.svelte";
    import Logo from "./components/Identity/Logo.svelte";
    import Smoke from "./components/Identity/Smoke.svelte";
    import Typography from "./components/Identity/Typography.svelte";

    
    let step = 1, last = 5

    function next() {
        if(step < last) { step++; return }
        if(step = last) { step = 1; return }
    }

    function prev() {
        if(step == 1) { step = last; return }
        if(step <= last) { step--; return }
    }


</script>

<div class="container">
    <div class="navbtn left" on:click={prev} on:keypress={prev}></div>
    <div class="navbtn right" on:click={next} on:keypress={next}></div>
    {#if step == 1}
        <Logo/>
    {/if}
    {#if step == 2}
        <BwLogo/>
    {/if}
    {#if step == 3}
        <Colors/>
    {/if}
    {#if step == 4}
        <Smoke/>
    {/if}
    {#if step == 5}
        <Typography/>
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
    

    @media screen and (last-width: 750px) {
        .navbtn {
            width: 10vw;
        }
    }
    @media screen and (last-width: 300px) {
        .navbtn {
            width: 15vw;
        }
    }
</style>