<script>
    import Legend from "./components/Legend.svelte";
    import Sources from "./components/Sources.svelte";
    import Stickers from "./components/Stickers.svelte";
    import Telegram from "./components/Telegram.svelte";
    
    let content = Legend
    let active = [true, '', '', '']
    let height = window.innerHeight * 0.01
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
    }, true);
</script>

<div class="container">
    <div class="title-box">
        <span class="title">Знакомтесь, </span>
        <span class="gradient title">Феня!</span>
    </div>
    <div class="menu-box" style="height: {height * 60}px;">
        <div class="content">
            <svelte:component this="{content}"/>
        </div>
        <div class="menu">
            <div active="{active[0]}" class="menu-link" on:click={() => { content = Legend; active = [true, '', '', ''] }} on:keypress={() => { content = Legend; active = [true, '', '', ''] }}>Легенда</div>
            <div active="{active[1]}" class="menu-link" on:click={() => { content = Stickers; active = ['', true, '', ''] }} on:keypress={() => { content = Stickers; active = ['', true, '', ''] }}>Стикеры</div>
            <div active="{active[2]}" class="menu-link" on:click={() => { content = Sources; active = ['', '', true, ''] }} on:keypress={() => { content = Sources; active = ['', '', true, ''] }}>Исходники</div>
            <div active="{active[3]}" class="menu-link" on:click={() => { content = Telegram; active = ['', '', '', true] }} on:keypress={() => { content = Telegram; active = ['', '', '', true] }}>Telegram</div>
        </div>
    </div>
</div>

<style>

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

    .menu-link[active="true"]:after {
        display: block;
        position: absolute;
        left: 0;
        width: 0;
        height: 5px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        content: "";
        width: 100%;
    }
    .menu-link[active="true"] {
        opacity: 1;
        font-size: 4vh;
    }

    .content {
        width: 70%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
    }
    .menu {
        width: 30%;
        height: 100%;
        background-color: #FFFFFF;
        border-radius: 1vw;
        filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.25));
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
    }
    .menu-box {
        margin-top: 50px;
        width: 80%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        align-content: stretch;
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
    .gradient.title {
        text-align:center;
        color:#191335;
        background-image:linear-gradient(to right, #FF00E5 0%, #0094FF 33.33333%, #0094FF 0% 66.66666%, #FF00E5);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        background-size: 300% 100%;
        background-position: top left;
        transition:all 1s ease-in-out;
        cursor: default;
    }

    .gradient.title:hover {
        background-position: top left 100%;
    }

    .title {
        font-size: 7vw;
    }

    @media screen and (orientation:portrait) {
        .menu-box {
            display: flex;
            flex-direction: column;
            flex-wrap: nowrap;
            justify-content: space-between;
            align-items: center;
            align-content: stretch;
            width: 100%;
            height: 100%;
        }
        .menu {
            width: 100%;
            height: 30%;    
            background-color: rgba(0, 0, 0, 0);
        }
        .content {
            width: 100%;
            height: 70%;
        }
    }

</style>