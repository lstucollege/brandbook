<script>
    import { img } from '../../../scripts/renders'
    import GoodsCard from "../GoodsCard.svelte";

    let links = `
        ${img.stickerpack1}
        ,
        ${img.stickerpack2}
        ,
        ${img.stickerpack1}
        ,
        ${img.stickerpack2}
    `

    let title = 'Стикерпак'

    let sections = `
        { "title": "Описание" , "text": "Благодаря большому вниманию к маскоту УК, у нас появится свой стикерпак, который будет отличным призом за победу/участие в любом конкурсе."}
    `

    let file = {
        name: 'stickerpack.zip',
        url: 'https://disk.yandex.ru/d/CybqoQ4VU2HuRw'
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
