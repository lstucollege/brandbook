<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.sticker1}
        ,
        ${img.sticker2}
        ,
        ${img.sticker1}
        ,
        ${img.sticker2}
    `

    let title = 'Стикер'

    let sections = `
        { "title": "Описание" , "text": "Наклейки можно наклеить куда угодно: на любимую планшетку, рабочий ноутбук, чехол или повербанк."}
    `

    let file = {
        name: 'sticker-single.zip',
        url: 'https://disk.yandex.ru/d/lpTax_SXWcO7gg'
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
