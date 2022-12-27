<script>
    import icon from '../img/figma.svg'
</script>

<div class="container">
    <div class="title">УНИВЕРСИТЕТСКИЙ КОЛЛЕДЖ</div>
    <div class="circle"></div>
    <a class="figma" href="https://www.figma.com/file/7f9FJnuVAkNSzLw48rFAM1/%D0%A3%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%82%D0%B5%D1%82%D1%81%D0%BA%D0%B8%D0%B9-%D0%BA%D0%BE%D0%BB%D0%BB%D0%B5%D0%B4%D0%B6?node-id=753%3A304&t=JEjxOcFtaaxaZSLC-1" target="_blank" rel="noreferrer">
        <img src="{icon}" alt="" class="icon">
        <div class="text">Открыть в Figma</div>
    </a>
</div>



<style>

    .text {
        font-size: 1.5vw;
        color: #FFFFFF;
    }

    .figma:hover {
        opacity: .5;
        transition: .5s;
    }

    .figma {
        transition: .5s;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 10px 20px;
        gap: 20px;
        box-sizing: border-box;
        background: #0C0C0C;
        border-radius: 10px;
        text-decoration: none;
        position: absolute;
        bottom: 10%; right: 50%;
        transform: translate(50%,-50%);
    }
    .circle {
        width: 50vw;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        height: 50vw;
        border-radius: 100%;
    }
    .title {
        position: absolute;
        right: 0px;
        top: 0px;
        font-size: 6vw;
        line-height: 90%;
        text-align: right;
        color: #0C0C0C;
        mix-blend-mode: color-burn;
    }
    .container {
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
    }

    @media screen and (orientation:portrait) {
        .text {
            font-size: 2vh;
        }
    }
</style>
