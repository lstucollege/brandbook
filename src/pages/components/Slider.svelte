<script>
    export let w = '500', h = '500', links = ''
    let linkArray = links.split(',')

    let maxLenght = Number(w) * linkArray.length
    let currentLenght = 0

    function next() {
        currentLenght = currentLenght + Number(w)
        if ( currentLenght == maxLenght ) currentLenght = 0
    }

    function prev() {
        currentLenght = currentLenght - Number(w)
        if ( currentLenght < 0 ) currentLenght = maxLenght - Number(w)
    }
</script>

<div class="slider" style="width: {w}px; height: {h}px">
    <div class="images" style="width: {maxLenght}px; height: {h}px; left: -{currentLenght}px">
        {#each linkArray as link}
        <img src="{link}" alt="" class="slider-item" style="width: {w}px; height: {h}px">
        {/each}
    </div>
    <div class="navbtn left" on:click={prev} on:keypress={prev}></div>
    <div class="navbtn right" on:click={next} on:keypress={next}></div>
</div>

<style>
    .slider {
        overflow-x: hidden;
        overflow-y: hidden;
        position: relative;
        border-radius: 25px;
        user-select: none;
        background-color: white;
        filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.25));
    }

    .slider-item {
        object-fit: cover;
        z-index: 9;
    }

    .images {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: stretch;
        position: absolute;
        pointer-events: none;
    }
    

    .navbtn {
        width: 10%;
        height: 100%;
        transition: .5s;
        cursor: pointer;
        z-index: 10;
        position: absolute;
        top: 0px;
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
</style>