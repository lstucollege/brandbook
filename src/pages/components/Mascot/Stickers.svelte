<script>
    import { stickers } from "../../../scripts/stickers";
    let height = window.innerHeight * 0.01
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
    }, true);
</script>

<div class="slider">
    {#each stickers as item}
    <img src="{item.img}" alt="" style="height: {height * 45}px">
        <!-- <img src="{item.img}" alt="" class="sticker"> -->
    {/each}
</div>

<style>
    .slider {
        scroll-snap-type: x mandatory;
        overflow-x: overlay;
        overflow-y: hidden;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: stretch;
    }

</style>