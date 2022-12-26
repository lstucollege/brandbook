<script>
    import font from './style/font-face.css'
    import menuImg from './img/menu.svg'
    import typo from './img/typo.svg'
    import Main from './pages/Main.svelte';
    import { page } from './scripts/menu'
    import { onMount } from 'svelte';
    import Philosophy from './pages/Philosophy.svelte';
    import Identity from './pages/Identity.svelte';
    import Mascot from './pages/Mascot.svelte';
    import Souvenir from './pages/Souvenir.svelte';
    import Font from './pages/Font.svelte';
    import Smm from './pages/SMM.svelte';
    import Hint from './pages/components/Hint.svelte';
    import woff from './style/DelaGothicOne-Regular.woff'
    import woff2 from './style/DelaGothicOne-Regular.woff2'
    import Contacts from './pages/Contacts.svelte';
    import Guide from './pages/Guide.svelte';
    onMount(() => {
        page.set(Main)
    })
    let menuLinks = [
        { page: Main, name: 'ГЛАВНАЯ' },
        { page: Philosophy, name: 'ФИЛОСОФИЯ' },
        { page: Identity, name: 'АЙДЕНТИКА' },
        { page: Guide, name: 'ГАЙДЛАЙНЫ' },
        { page: Mascot, name: 'МАСКОТ' },
        { page: Souvenir, name: 'СУВЕНИРКА' },
        { page: Font, name: 'ШРИФТЫ' },
        { page: Smm, name: 'SMM' },
        { page: Contacts, name: 'КОНТАКТЫ' }
    ]
    let state = false

    function menuHandler() {
        if (state == false) { state = true; return }
        if (state == true) { state = false; return }
    }

    window.addEventListener('resize', function(event) {
        document.documentElement.style.setProperty('--vh', `${window.innerHeight * 0.01}px`)
    }, true);
    
</script>

<svelte:head>
    <link rel="preload" href="{woff}" as="font" type="font/woff" crossorigin>
    <link rel="preload" href="{woff2}" as="font" type="font/woff2" crossorigin>
</svelte:head>

<Hint text="Большинство элементов интерактивные! Развлекайтесь!"/>
<main>
    <nav>
        <img src="{menuImg}" alt="" class="menu-btn" on:click={menuHandler} on:keypress={menuHandler}>
    </nav>
    {#if state == true}
        <div class="menu">
            {#each menuLinks as item}
                <div class="menu-link" on:click={() => { page.set(item.page); state = false }} on:keypress={() => { page.set(item.page); state = false }}>{item.name}</div>
            {/each}
        </div>
    {/if}
    {#if state == false}
        <section>
            <svelte:component this="{$page}"/>
        </section>
    {/if}
        <footer>
            <img class="typo-logo" src="{typo}" alt="Developed by TYPO"/>
            <a href="https://github.com/typodevstudio" class="typo-link">github</a>
            <a href="https://vk.com/typodesigner" class="typo-link">vk</a>
            <a href="https://www.behance.net/typostudio" class="typo-link">behance</a>
        </footer>
</main>

<style>
    .menu-btn {
        height: 3vh;
        cursor: pointer;
        transition: .5s ;
    }

    .menu-btn:hover {
        opacity: .5;
        transition: .5s ;
    }
    .menu {
        position: relative;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        width: 100%;
        height: 80%;
        box-sizing: border-box;
    }
    .menu-link {
        position: relative;
        color: #0C0C0C;
        cursor: pointer;
        line-height: 1;
        text-decoration: none;
        font-size: 3vh;
        opacity: .5;
        transition: .5s ;
        margin-top: 15px;
    }

    .menu-link:hover {
        opacity: 1;
        font-size: 4vh;
        transition: .5s ;
    }
    .menu-link:after {
        display: block;
        position: absolute;
        left: 0;
        width: 0;
        height: 5px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        content: "";
        transition: width 0.3s ease-out;
    }

    .menu-link:hover:after,
    .menu-link:focus:after {
        width: 100%;
    }
    :global(body) {
        margin: 0;
        background: linear-gradient(112.35deg, #FA1515 -197.95%, rgba(253, 32, 32, 0) 20.81%), linear-gradient(69.33deg, #69DDED -82.09%, rgba(152, 230, 240, 0) 47.26%), linear-gradient(247.87deg, #F5F7B7 -79.59%, rgba(243, 252, 207, 0) 62.31%), linear-gradient(285.94deg, #F49795 -137.26%, rgba(233, 46, 44, 0) 24.04%), linear-gradient(254.53deg, #6F37CA -16.76%, rgba(111, 55, 202, 0.66) -16.75%, rgba(189, 70, 208, 0) 22.09%), #F0F1F2;
        width: 100vw;
        height: calc(var(--vh, 1vh) * 100);
        font-family: 'Dela Gothic One', cursive;
        overflow: hidden;
        color: #0C0C0C;
    }

    main {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: flex-end;
        align-content: stretch;
        height: calc(var(--vh, 1vh) * 100);
        width: 100%;
        overflow: hidden;
    }

    nav {
        height: 10%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-end;
        padding: 0px 3vw;
        gap: 50px;
        box-sizing: border-box;
        overflow: hidden;
    }

    section {
        position: relative;
        width: 100%;
        height: 80%;
        box-sizing: border-box;
    }

    footer {
        width: 100%;
        height: 10%;
        display: flex;
        flex-direction: row;
        align-items: center;
        padding: 0px 3vw;
        gap: 50px;
        box-sizing: border-box;
        overflow: hidden;
    }

    .typo-link {
        position: relative;
        color: #0C0C0C;
        cursor: pointer;
        line-height: 1;
        text-decoration: none;
        font-size: 2vh;
        opacity: .5;
        transition: .5s ;
    }

    .typo-link:hover {
        opacity: 1;
        font-size: 2.2vh;
        transition: .5s ;
    }
    .typo-link:after {
        display: block;
        position: absolute;
        left: 0;
        width: 0;
        height: 2px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        content: "";
        transition: width 0.3s ease-out;
    }

    .typo-link:hover:after,
    .typo-link:focus:after {
        width: 100%;
    }

    .typo-logo {
        height: 3vh;
        cursor: pointer;
        transition: .5s ;
    }

    .typo-logo:hover {
        height: 3.1vh;
        opacity: .5;
        transition: .5s ;
    }
    /* Firefox */
    :global(*) {
        scrollbar-width: thin;
        scrollbar-color: #0C0C0C #FFFFFF;
    }

    /* Chrome, Edge and Safari */
    :global(::-webkit-scrollbar) {
        width: 5px;
        height: 5px;
    }
    :global(::-webkit-scrollbar-track) {
        border-radius: 5px;
        opacity: 0;
    }

    :global(::-webkit-scrollbar-track:hover) {
        opacity: 0;
    }

    :global(::-webkit-scrollbar-track:active) {
        opacity: 0;
    }

    :global(::-webkit-scrollbar-thumb) {
        border-radius: 5px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        width: 5px;
        height: 5px;
        cursor: pointer;
    }

    :global(::-webkit-scrollbar-thumb:hover) {
        opacity: .5;
    }

    :global(::-webkit-scrollbar-thumb:active) {
        opacity: .2;
    }
    :global(::selection) {
        background: #ae00ff59;
    }
    :global(::-moz-selection) {
        background: #ae00ff59;
    }

    @media screen and (max-width: 800px) {
        footer {
            justify-content: space-around;
            gap: 2vw;
        }
        .typo-link { font-size: 1.5vh; }
        .typo-link:hover { font-size: 1.7vh; }
        .menu-btn:hover { opacity: 1; }
    }
</style>
