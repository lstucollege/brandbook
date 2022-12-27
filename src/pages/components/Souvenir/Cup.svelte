<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.stakan1}
        ,
        ${img.stakan2}
        ,
        ${img.stakan1}
        ,
        ${img.stakan2}
    `

    let title = 'Термокружка'

    let sections = `
        { "title": "Описание" , "text": "То, ради чего нужно внести довольно большой вклад в развитие профбюро УК. Также выполнена в корпоративных цветах. На ней будет стильно и гордо носиться наш фирменный резиновый браслет!"}
    `

    let file = {
        name: 'cup.zip',
        url: 'https://disk.yandex.ru/d/oY49bGN8wvTlMw'
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
