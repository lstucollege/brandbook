<script>
    import { sticker } from '../../../scripts/stickers'

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

<img src="{sticker.tricky}" alt="" class="tricky" id="sticker">
<div class="banner">
    <span class="line left one">Перетягиваем</span>
    <span class="line title center two" on:mouseenter={img.showShadow} on:mouseleave={img.hideShadow}>ВНИМАНИЕ</span>
    <span class="line right three">на действительно</span>
    <span class="line title center four" on:mouseenter={img.show} on:mouseleave={img.hide}>ВАЖНЫЕ</span>
    <span class="line right five">вещи</span>
</div>

<style>

    .center {
        text-align: center;
    }

    .left {
        text-align: left;
    }

    .right {
        text-align: right;
    }
    .tricky {
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
        transition: .5s;
    }

    .title:hover {
        background-position: top left 100%;
        opacity: .7;
        transition: .5s;
    }
</style>