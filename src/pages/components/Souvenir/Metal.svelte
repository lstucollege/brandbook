<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.metal1}
        ,
        ${img.metal2}
        ,
        ${img.metal3}
        ,
        ${img.metal4}
    `

    let title = 'Значок (металл)'

    let sections = `
        { "title": "Описание" , "text": "Ещё одна вещь, которую заслуживают немногие. Маленькая, но такая ценная для её обладателя. Такие выдают за крупные достижения "}
    `

    let file = {
        name: 'metal.zip',
        url: 'https://disk.yandex.ru/d/-JeqgZac75aiWg'
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
