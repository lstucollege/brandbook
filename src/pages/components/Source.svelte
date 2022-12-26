<script>
    export let url, name = 'с Яндекс.Диска', width = '400px', height = '100px'
    import logo from '../../img/drive-logo.svg'
</script>

<a class="button" href="{url}" target="_blank" rel="noreferrer" style="width: {width}; height: {height};">
    <img src="{logo}" alt="" class="drive-logo">
    <div class="text-container">
        <div class="title">Скачать исходники</div>
        <div class="name">{name}</div>
    </div>
    <span class="flare"></span>
</a>

<style>
    .button {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 0px 50px;
        gap: 10px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        border-radius: 15px;
        text-decoration: none;
        position: relative; 
        overflow: hidden;
        box-sizing: border-box;
        transition: .5s;
    }

    .button:hover {
        opacity: .7;
        transition: .5s;
    }

    .drive-logo {
        height: 50%;
    }

    .title {
        font-size: 2vh;
        color: #FFFFFF;
    }

    .name {
        font-size: 1.5vh;
        color: #FFFFFF;
        opacity: 0.5;
    }

    .flare {
        position: absolute;
        top: 0;
        height: 100%;
        width: 45px;
        transform: skewX(-45deg);
        animation: flareAnimation;
        left: -150%;
        background: linear-gradient(90deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.4));
        animation: flareAnimation 2s infinite linear;
        filter: blur(10px);
    }

    @keyframes flareAnimation {
        0% {
            left: -150%;
        }
        100% {
            left: 150%;
        }
    }
</style>