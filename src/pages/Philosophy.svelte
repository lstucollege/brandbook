<script>
    import { sticker } from '../scripts/stickers'
    let title = 'ПРОСТРАНСТВО'; title.split('')

    let step = 1, max = 2

    function next() {
        if(step < max) { step++; return }
        if(step = max) { step = 1; return }
    }

    function prev() {
        if(step == 1) { step = max; return }
        if(step <= max) { step--; return }
    }

    document.addEventListener('swiped-right', () => prev());
    document.addEventListener('swiped-left', () => next());

    let img = {
        hide: () => {
            document.querySelector('#sticker').style = 'opacity: .2; width: 100vw; transition: .5s;'
        },
        show: () => {
            document.querySelector('#sticker').style = 'opacity: .8; width: 130vw; transition: .5s;'
        },
        hideShadow: () => {
            document.querySelector('#sticker').style = 'filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0)); transition: .5s;'
        },
        showShadow: () => {
            document.querySelector('#sticker').style = 'filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 1)); transition: .5s;'
        }
    }
</script>

<div class="container">
    <div class="navbtn left" on:click={prev} on:keypress={prev}></div>
    <div class="navbtn right" on:click={next} on:keypress={next}></div>
    {#if step == 1}
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
    {/if}

    {#if step == 2}
        <img src="{sticker.tricky}" alt="" class="tricky" id="sticker">
        <div class="banner">
            <span class="line left one">Перетягиваем</span>
            <span class="line title center two" on:mouseenter={img.showShadow} on:mouseleave={img.hideShadow}>ВНИМАНИЕ</span>
            <span class="line right three">на действительно</span>
            <span class="line title center four" on:mouseenter={img.show} on:mouseleave={img.hide}>ВАЖНЫЕ</span>
            <span class="line right five">вещи</span>
        </div>
    {/if}
</div>

<style>


    .tricky {
        position: absolute;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 100vw;
        pointer-events: none;
        opacity: .2;
        z-index: -5;
        transition: .5s;
    }

    .line.one {
        font-size: 2vw;
    }

    .line.two {
        font-size: 5.3vw;
        z-index: 5;
    }

    .line.three {
        font-size: 3vw;
    }

    .line.four {
        font-size: 4vw;
        z-index: 5;
    }

    .line.five {
        font-size: 4vw;
        margin-top: -1.5vw;
    }

    .line {
        width: 100%;
        margin-bottom: -1.5vw;
    }

    .left {
        text-align: left;
    }

    .right {
        text-align: right;
    }

    .center {
        text-align: center;
    }
    .banner {
        width: 40vw;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: stretch;
        align-content: stretch;
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