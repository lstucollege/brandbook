<script>
    import Bag from "./components/Souvenir/Bag.svelte";
    import Braclet from "./components/Souvenir/Braclet.svelte";
    import Cup from "./components/Souvenir/Cup.svelte";
    import Metal from "./components/Souvenir/Metal.svelte";
    import Pin from "./components/Souvenir/Pin.svelte";
    import Sticker from "./components/Souvenir/Sticker.svelte";
    import Stickerpack from "./components/Souvenir/Stickerpack.svelte";
    import Wood from "./components/Souvenir/Wood.svelte";
    import { img } from "../scripts/renders";
    import Shirt from "./components/Souvenir/Shirt.svelte";
    import Hoodie from "./components/Souvenir/Hoodie.svelte";

    let height = window.innerHeight * 0.01
    let orient = 'landscape'
    let cfh = 20, cfw = 20 
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
        orient = 'landscape'
        if (window.innerHeight > window.innerWidth) orient = 'portrait'
        cfh = 20, cfw = 20 
        if (orient == 'portrait') cfh = 37, cfw = 37
    }
    , true);

    height = window.innerHeight * 0.01
    if (window.innerHeight > window.innerWidth) orient = 'portrait'
    if (orient == 'portrait') cfh = 37, cfw = 37

    let items = [
        { page: Wood, title: 'Значок (Дерево)', img: img.wood4 },
        { page: Metal, title: 'Значок (Металл)', img: img.metal3 },
        { page: Pin, title: 'Значок', img: img.large4 },
        { page: Sticker, title: 'Стикер', img: img.sticker2 },
        { page: Stickerpack, title: 'Стикерпак', img: img.stickerpack2 },
        { page: Cup, title: 'Термокружка', img: img.stakan1 },
        { page: Braclet, title: 'Браслет', img: img.braclet1 },
        { page: Bag, title: 'Сумка', img: img.bag1 },
        { page: Shirt, title: 'Футболка', img: img.shirt2 },
        { page: Hoodie, title: 'Худи', img: img.hoodie2 },
    ]

    let itemState = false
    let currentPage
    function openPage(page) {
        itemState = true
        currentPage = page
    }
    function closePage() {
        itemState = false
    }
</script>
{#if itemState == true}
    <div class="back" on:click={closePage} on:keypress={closePage}>НАЗАД</div>
    <svelte:component this={currentPage}/>
{/if}
{#if itemState == false}
    <div class="container">
        <div class="gradient title">Сувенирная продукция</div>
        <div class="items">
            {#each items as item}
                <div class="item">
                    <div class="item-title">{item.title}</div>
                    <div class="image-container">
                        <img src="{item.img}" alt="" class="image" style="height: 100%; width: 100%;">
                    </div>
                    <div class="item-button" on:click={() => openPage(item.page)} on:keypress={() => openPage(item.page)}>
                        <div class="button-text">Подробнее</div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
{/if}



<style>

    .image {
        object-fit: contain;
    }

    .back {
        position: absolute;
        top: -7.7vh;
        left: 3.7vw;
        font-size: 3.7vh;
        transition: .5s;
        cursor: pointer;
    }

    .back:hover {
        opacity: .5;
        transition: .5s;
    }

    .container {
        width: 100%;
        height: 100%;
        overflow-x: hidden;
        overflow-y: scroll;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: stretch;
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
        font-size: 6vw;
    }
    .button-text {
        color: white;
        font-size: 70%;
    }

    .image-container {
        width: 100%;
        height: 100%;
    }

    .item-button {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        width: 80%;
        height: 50px;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        border-radius: 25px;
        cursor: pointer;
        transition: .5s;
    }

    .item-button:hover {
        opacity: .5;
        transition: .5s;
    }
    .item-title {
        width: 100%;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        font-size: 1.5vw;
        text-align: center;
    }
    .item {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        border-radius: 25px;
        user-select: none;
        background-color: white;
        filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.25));
        width: 20vw;
        height: 25vw;
        box-sizing: border-box;
        padding: 15px 15px;
    }
    .items {
        margin-top: 25px;
        display: grid; 
        grid-template-columns: 1fr 1fr 1fr 1fr; 
        gap: 25px 25px; 
        grid-template-areas: 
            ". . . ."
            ". . . ."
            ". . . ."; 
        justify-content: center; 
        align-content: center; 
        justify-items: center; 
        align-items: center; 
        max-width: 1920px;
    }

    @media screen and (orientation:portrait) {
        .items {
            grid-template-columns: 1fr; 
            gap: 25px 25px; 
            grid-template-areas: 
                "."
                "."
                "."
                "."; 
                width: 100%;
    
        }
        .item {
            width: 70vw;
            height: 70vw;
        }
        .item-title {
            font-size: 4vw;
        }
        .image-container {
            height: 70%;
        }
    }
</style>

