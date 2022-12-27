<script>
    import Slider from "./Slider.svelte";
    import Source from './Source.svelte'
    export let links = '', title = 'Заголовок', fileName = 'с Яндекс.Диска', fileUrl,  section = `{ "title": "Описание" , "text": "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita, veniam magni? Et, velit assumenda? Corrupti."}`
    let sections = section.split('|')

    for (let i = 0; i < sections.length; i++) {
        let parsed = JSON.parse(sections[i])
        sections[i] = parsed 
    }

    let height = window.innerHeight * 0.01
    let orient = 'landscape'
    let cfh = 50, cfw = 50 
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
        orient = 'landscape'
        if (window.innerHeight > window.innerWidth) orient = 'portrait'
        cfh = 50, cfw = 50 
        if (orient == 'portrait') cfh = 37, cfw = 37
    }
    , true);

    
    height = window.innerHeight * 0.01
    if (window.innerHeight > window.innerWidth) orient = 'portrait'
    if (orient == 'portrait') cfh = 37, cfw = 37
    
</script>

<div class="container">
    <Slider links={links} w={height*cfh} h={height*cfw}/>
    <div class="description" style="height: {height*cfh}px; width: {height*cfw}px;">
        <div class="title">{title}</div>
        {#each sections as item }
            <div class="subtitle">{item.title}</div>
            <div class="text">{item.text}</div>
        {/each}
        <div class="button">
            <Source url="{fileUrl}" name="{fileName}" width="100%" height="100%"/>
        </div>
    </div>
</div>


<style>

    .button {
        width: 80%;
        height: 100px;
    }

    .text {
        font-size: 24px;
        color: #0C0C0C;
        width: 90%;
        word-break: break-word;
    }
    .subtitle {
        width: 100%;
        font-size: 32px;
        color: #0C0C0C;
        text-align: center;
    }
    
    .title {
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        font-size: 6vh;
        text-align: center;
        width: 100%;
    }

    .description {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 15px 0px;
        gap: 10px;
        overflow-x: hidden;
        overflow-y: scroll;
    }

    .container {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        gap: 15px;
    }

    @media screen and (orientation :portrait) {
        .container {
            flex-direction: column;
        }
        .button {
            width: 95%;
        }
        .description {
            gap: 5px;
        }
    }
</style>


