<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.large1}
        ,
        ${img.large2}
        ,
        ${img.large3}
        ,
        ${img.large4}
    `

    let title = 'Значок'

    let sections = `
        { "title": "Описание" , "text": "Мелкий раздаточный материал, 38 мм в диаметре, который сможет украсить любую футболку или рюкзак и является неотъемлемой частью нашей корпоративной культуры"}
    `

    let file = {
        name: 'pin.zip',
        url: 'https://disk.yandex.ru/d/Pgs1Tv-lubIStw'
    }
</script>


<div class="container">
    <GoodsCard links="{links}", title="{title}" section="{sections}" fileName="{file.name}" fileUrl="{file.url}"/>
</div>

<style>
    .container {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        width: 100%;
        height: 100%;
    }
</style>
