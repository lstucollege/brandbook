<script>
    import Source from "./Source.svelte";

    export let img, title, text, url, name

    let blockCF = 40, imgCF = 30

    let height = window.innerHeight * 0.01
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
        if(window.innerHeight > window.innerWidth){
            blockCF = 30
        }
    }, true);
    if(window.innerHeight > window.innerWidth){
        blockCF = 30
    }
</script>

<div class="mobile-title" style="font-size: {height * 4}px;">
    {title}
</div>

<div class="container">
    <div class="image block" style="height: {height * blockCF}px;">
        <img src="{img}" alt="" class="image" style="height: {height * imgCF}px;">
    </div>
    <div class="text block" style="height: {height * blockCF}px;">
        <div class="title" style="font-size: {height * 4}px;">{title}</div>
        <div class="description">
            {text}
        </div>
    </div>
</div>

<div class="source">
    <Source url="{url}" name="{name}" width="100%" height="100%"/>
</div>



<style>

    .mobile-title {
        display: none;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        width: 100%;
        height: 17%;
        text-align: center;
        position: absolute;
        top: 7%; 
        right: 50%;
        transform: translate(50%,-50%);
    }
    .source {
        position: absolute;
        bottom: -5%; 
        right: 50%;
        width: 40vw;
        height: 100px;
        transform: translate(50%,-50%);
    }

    .description {
        width: 100%;
        height: 80%;
        overflow-y: scroll;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: stretch;
    }

    .title {
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        width: 100%;
        height: 17%;
        text-align: center;
    }
    
    .container {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
    }

    .image {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        filter: drop-shadow(0px 0px 5px rgba(0, 0, 0, 0.1));
    }

    .text {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        align-content: stretch;
    }

    .block {
        width: 30vw
    }
    
    @media screen and (orientation:portrait) {
        .container {
            flex-direction: column;
        }

        .block {
            width: 80vw;
        }

        .source {
            width: 80vw;
            height: 10vh;
        }

        .mobile-title {
            display: block;
        }

        .title {
            display: none;
        }
        
        .text {
            margin-top: 25px;
        }
    }
</style>