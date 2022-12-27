<script>
    import Source from "./components/Source.svelte";
    import head_ny from '../img/smm/head-ny.png'
    import head from '../img/smm/head.png'
    import p_image_ny from '../img/smm/p-image-ny.png'
    import p_image from '../img/smm/p-image.png'
    import widget_1 from '../img/smm/widget-1.png'
    import widget_2 from '../img/smm/widget-2.png'
    import widget_3 from '../img/smm/widget-3.png'
    import widget_1_ny from '../img/smm/widget-1-ny.png'
    import widget_2_ny from '../img/smm/widget-2-ny.png'
    import widget_3_ny from '../img/smm/widget-3-ny.png'
    import snow from '../img/smm/snow.png'
    import sun from '../img/smm/sun.png'

    let height = window.innerHeight * 0.01
    let orient = 'landscape'
    let cfh = 50, cfw = 50 
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
        orient = 'landscape'
        if (window.innerHeight > window.innerWidth) orient = 'portrait'
        cfh = 50, cfw = 50 
        if (orient == 'portrait') cfh = 37, cfw = 37
    }
    , true);

    
    height = window.innerHeight * 0.01
    if (window.innerHeight > window.innerWidth) orient = 'portrait'
    if (orient == 'portrait') cfh = 37, cfw = 37

    let black = {
        head: head_ny,
        image: p_image_ny,
        widget: [ widget_1_ny, widget_2_ny, widget_3_ny ],
        icon: sun,
        text: '#FFFFFF',
        color: '#0C0C0C'
    }

    let white = {
        head: head,
        image: p_image,
        widget: [ widget_1, widget_2, widget_3 ],
        icon: snow,
        color: '#FFFFFF',
        text: '#0C0C0C'
    }

    let current = white

    function switchTheme() {
        if (current == white) {current = black; return}
        if (current == black) {current = white; return}
    }
</script>

<div class="container" style="height: {height * 80}px;">
    <div class="social" style="background-color: {current.color};">
        <img src="{current.head}" alt="" class="head">
        <div class="head-info">
            <img src="{current.image}" alt="" class="image" style="border: 10px {current.color};">
            <div class="info">
                <div class="title-head" style="color: {current.text};">Университетский колледж ЛГТУ</div>
                <div class="subtitle-head" style="color: {current.text}; opacity: .5;">ЛУЧШИЙ КОЛЛЕДЖ МИРА</div>
            </div>
            <div class="change-container" on:click={switchTheme} on:keypress={switchTheme}>
                <div class="change" style="background-color: {current.text};">
                    <img src="{current.icon}" alt="" class="change-icon">
                </div>
            </div>
        </div>
        <div class="widget">
            <div class="item">
                <img src="{current.widget[0]}" alt="" class="item-image">
                <div class="item-info">
                    <div class="title" style="color: {current.text};">Никита Гребенюк</div>
                    <div class="subtitle" style="color: {current.text}; opacity: .5;">ЗАМ. ПО ОРГАНИЗАЦИОННОЙ РАБОТЕ</div>
                </div>
            </div>
            <div class="item">
                <img src="{current.widget[1]}" alt="" class="item-image">
                <div class="item-info">
                    <div class="title" style="color: {current.text};">Данил Маслов</div>
                    <div class="subtitle" style="color: {current.text}; opacity: .5;">ПРЕДСЕДАТЕЛЬ ПРОФБЮРО</div>
                </div>
            </div>
            <div class="item">
                <img src="{current.widget[2]}" alt="" class="item-image">
                <div class="item-info">
                    <div class="title" style="color: {current.text};">Дарья Крутилина</div>
                    <div class="subtitle" style="color: {current.text}; opacity: .5;">ЗАМ. ПО ВНЕУЧЕБНОЙ РАБОТЕ</div>
                </div>
            </div>
        </div>
        <div class="source">
            <Source url="https://disk.yandex.ru/d/oCRyTbfeJMGEvQ" name="smm.zip"/>
        </div>
    </div>
</div>


<style>
    .item-info {
        width: 100%;
        transition: .5s;
    }
    .item-image {
        width: 100%;
        transition: .5s;
    }

    .item {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 0px;
        gap: 15px;
        width: 30%;
        transition: .5s;
    }
    .widget {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 50px 0px;
        gap: 10px;
        width: 100%;
        transition: .5s;
    }

    .change-icon {
        height: 50%;
        transition: .5s;
        user-select: none;
    }
    .change {
        width: 3vw;
        height: 3vw;
        border-radius: 50%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        transition: .5s;
        cursor: pointer;
    }

    .change:hover {
        opacity: .5;
        transition: .5s;
    }
    .change-container {
        height: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        align-content: stretch;
        transition: .5s;
    }

    .info {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        padding: 15px;
        gap: 10px;
        box-sizing: border-box;
        height: 100%;
        width: 75%;
        transition: .5s;
    }
    .image {
        width: 20%;
        border-radius: 50%;
        transition: .5s;
    }

    .head-info {
        position: relative;
        width: 100%;
        height: 7vw;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: flex-end;
        align-content: stretch;
        padding: 0px 2.5vw;
        box-sizing: border-box;
        transition: .5s;
    }

    .title {
        font-size: 1.5vw;
        transition: .5s;
    }

    .subtitle {
        font-size: 0.7vw;
        transition: .5s;
    }

    .title-head {
        font-size: 1.5vw;
        transition: .5s;
    }

    .subtitle-head {
        font-size: 0.7vw;
        transition: .5s;
    }

    .head {
        width: 100%;
        border-radius: 15px;
        transition: .5s;
    }
    .container {
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: flex-start;
        align-content: stretch;
        overflow-y: overlay;
        overflow-x: hidden;
        transition: .5s;
    }

    .social {
        width: 70%;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: stretch;
        padding: 3%;
        position: relative;
        box-sizing: border-box;
        background: #FFFFFF;
        border-radius: 25px;
        transition: .5s;
    }

    @media screen and (orientation:portrait) {
        .social {
            width: 100%;
            border-radius: 15px;
        }
        .change {
            width: 10vw;
            height: 10vw;
            position: absolute;

        }
        .widget {
            flex-direction: column;
        }

        .title {
            font-size: 3vw;
        }

        .subtitle {
            font-size: 2vw;
        }
        .head-info {
            height: 15vw;
        }
        .item {
            width: 90%;
        }
        .change-container {
            width: 15%;
        }
        .title-head {
            font-size: 3vw;
            margin-bottom: -3vw;
        }
        .subtitle-head {
            font-size: 2vw;
        }
    }
</style>