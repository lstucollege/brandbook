<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.braclet1}
        ,
        ${img.braclet2}
        ,
        ${img.braclet3}
        ,
        ${img.braclet1}
        ,
        ${img.braclet2}
        ,
        ${img.braclet3}
    `

    let title = 'Браслет'

    let sections = `
        { "title": "Описание" , "text": "Сувенир, которого ещё нет ни у кого из Университетского колледжа засчёт своей новизны. Стильный и лаконичный браслет в двух корпоративных цветах, средней ширины, который может красоваться на термокружке, которая также есть в списке раздаточного материала!"}
    `

    let file = {
        name: 'braclet.zip',
        url: 'https://disk.yandex.ru/d/ppbvyqsgdAnshA'
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
