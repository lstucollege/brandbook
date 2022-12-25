<script>
    import { onMount } from "svelte";

    let display = 'flex'
    let hide = ''
    onMount(() => {
        setTimeout(() => {
            hide = 'hide'
        }, 5000)
        setTimeout(() => {
            display = 'none'
        }, 5500)
    })
</script>

<span class="hint {hide}" style="display: {display}">
    <img src="https://img.icons8.com/material-outlined/96/null/hint.png" alt="" class="hint-icon"/>
    <div class="hint-text">Большинство элементов интерактивные! Развлекайтесь!</div>
</span>

<style>

    .hint-icon {
        width: 25px;
        height: 25px;
    }
    .hint {
        padding: 10px 25px;
        border-radius: 50px;
        background-color: white;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: center;
        gap: 15px;
        position: absolute;
        bottom: 10%; 
        right: 50%;
        transform: translate(50%,-50%);
        user-select: none;
        pointer-events: none;
        box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
        opacity: 1;
        transition: .5s;
        z-index: 10000;
    }

    .hint.hide {
        opacity: 0;
        transition: .5s;
    }

    @media screen and (orientation:portrait) {
        .hint-text {
            font-size: 2vw;
        }
        .hint {
            width: 70vw;
        }
    }
</style>