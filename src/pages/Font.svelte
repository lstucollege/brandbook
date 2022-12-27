<script>
    import Source from "./components/Source.svelte";

    let eng = `Whereas disregard and contempt for human rights have resulted`
    let ru = 'Принимая во внимание, что пренебрежение и презрение к правам человека'
    let numbers = '1234567890'
    let symbols = '!@#$%^&*(){}[]":;/?|\\'
    let current = ru
    let active = [ true, false, false, false ]
</script>

<div class="container">
    <div class="gradient title">Dela Gothic One</div>
    <div class="template">{current}</div>
    <div class="source">
        <Source name="DelaGothicOne-Regular.ttf" url="https://disk.yandex.ru/d/OrTd-NssVOZgtA" width="100%" height="100%"/>
    </div>
    <div class="lang">
        <div class="switch" on:click={() => { active = [true, false, false, false]; current = ru }} on:keypress={() => { active = [true, false, false, false]; current = ru }} active="{active[0]}">RU</div>
        <div class="switch" on:click={() => { active = [false, true, false, false]; current = eng }} on:keypress={() => { active = [false, true, false, false]; current = eng }} active="{active[1]}">ENG</div>
        <div class="switch" on:click={() => { active = [false, false, true, false]; current = numbers }} on:keypress={() => { active = [false, false, true, false]; current = numbers }} active="{active[2]}">123</div>
        <div class="switch" on:click={() => { active = [false, false, false, true]; current = symbols }} on:keypress={() => { active = [false, false, false, true]; current = symbols }} active="{active[3]}">!?#</div>
    </div>
</div>

<style>
    .source {
        width: 40%;
        height: 100px;
    }

    .switch {
        width: 60px;
        height: 20px;
        color: #0C0C0C;
        border: 2px solid #0C0C0C;
        background-color: white;
        border-radius: 10px;
        text-align: center;
        line-height: 110%;
        cursor: pointer;
        transition: .5s;
    }

    .switch:hover {
        opacity: .7;
        transition: .5s;
    }

    .switch[active="true"] {
        border: 2px solid #0C0C0C;
        background-color: #0C0C0C;
        color: white;
        transition: .5s;
    }

    .lang {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        gap: 10px;
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
        width: 100%;
        font-size: 6vw;
        text-align: center;
    }

    .template {
        width: 80%;
        font-size: 6vh;
        text-align: center;
    }

    .container {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        align-content: stretch;
        height: 100%;
        width: 100%;
    }

    @media screen and (orientation:portrait) {
        .template {
            font-size: 9vw;
        }
        .title {
            font-size: 9vw;
        }
        .source {
        width: 90%;
        height: 100px;
    }
    }
</style>