<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.wood1}
        ,
        ${img.wood2}
        ,
        ${img.wood3}
        ,
        ${img.wood4}
    `

    let title = 'Значок (дерево)'

    let sections = `
        { "title": "Описание" , "text": "Таких значков не было ещё ни у кого. Фирменный стиль, фирменная раздатка... Да мы самые оригинальные. Если увидите деревянный значок у студента, то он либо с Посвята, либо этот человек – студент УК:)"}
    `

    let file = {
        name: 'wood.zip',
        url: 'https://disk.yandex.ru/d/mMID_7u5R5vvZA'
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
