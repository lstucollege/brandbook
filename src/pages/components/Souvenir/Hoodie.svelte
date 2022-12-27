<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.hoodie1}
        ,
        ${img.hoodie2}
        ,
        ${img.hoodie3}
        ,
        ${img.hoodie1}
        ,
        ${img.hoodie2}
        ,
        ${img.hoodie3}
    `

    let title = 'Худи'

    let sections = `
        { "title": "Описание" , "text": "Корпоративные цвета, вышитый логотип и признание большой проделанной работы и вклада в профбюро – первые ассоциации с этой вещью. Получить её может руководство или люди, которые также долго и упорно помогали нашему профбюро развиваться!"}
    `

    let file = {
        name: 'hoodie.zip',
        url: 'https://disk.yandex.ru/d/PlO8hEd3z0T4Hw'
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
