<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.shirt1}
        ,
        ${img.shirt2}
        ,
        ${img.shirt3}
        ,
        ${img.shirt1}
        ,
        ${img.shirt2}
        ,
        ${img.shirt3}
    `

    let title = 'Футболка'

    let sections = `
        { "title": "Описание" , "text": "Лаконичный дизайн – основная идея дизайна этой вещи. Обязательное наличие фирменного логотипа на сердце как признак преданности своему колледжу. Просто и со смыслом."}
    `

    let file = {
        name: 'shirt.zip',
        url: 'https://disk.yandex.ru/d/iVRS2wU95IqtvQ'
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
