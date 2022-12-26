<script>
    let title = 'ПРОСТРАНСТВО'; title.split('')
</script>

<div class="title">Философия стиля</div>
<div class="title-box">
    {#each title as symbol}
        <div class="symbol-box">
            <div class="symbol">{symbol}</div>
            <div class="symbol symbol-outer one">{symbol}</div>
            <div class="symbol symbol-outer two">{symbol}</div>
            <div class="symbol symbol-outer three">{symbol}</div>
            <div class="symbol symbol-outer four">{symbol}</div>
        </div>
    {/each}
</div>

<style>
    .title-box {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        user-select: none;
    }

    .symbol-box {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        opacity: .5;
        transition: .5s;
    }

    .symbol {
        font-size: 7vw;
    }

    .symbol-outer {
        margin-top: -8.7vw;
        color: transparent;
        -webkit-text-stroke: 1px black;
    }

    .symbol-outer.one {
        opacity: .8;
    }
    .symbol-outer.two {
        opacity: .6;
    }
    .symbol-outer.three {
        opacity: .4;
    }
    .symbol-outer.four {
        opacity: .2;
    }

    .symbol-box:hover {
        opacity: 1;
        transition: .5s;
    }
    
    .title {
        font-size: 3vw;
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

    .title:hover {
        background-position: top left 100%;
    }
</style>