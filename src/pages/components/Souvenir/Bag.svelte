<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.bag1}
        ,
        ${img.bag2}
        ,
        ${img.bag1}
        ,
        ${img.bag2}
    `

    let title = 'Сумка'

    let sections = `
        { "title": "Описание" , "text": "Нужная, компактная, но такая памятная вещь. В которую, к слову, можно сложить всю мелкую фирменную раздатку УК:)"}
    `

    let file = {
        name: 'bag.zip',
        url: 'https://disk.yandex.ru/d/fihNtZEVesvKBw'
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
