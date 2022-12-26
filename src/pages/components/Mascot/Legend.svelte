<script>
    let height = window.innerHeight * 0.01
    window.addEventListener('resize', function(event) {
        height = window.innerHeight * 0.01
    }, true);
</script>

<div class="legend" style="height: {height * 40}px">
    <span class="gradient title">Легенда маскота УК</span>
    <span class="text">
        Все мы видели его на логотипе Университетского колледжа, он есть в каждом посте. 
        Что уж там, даже у него есть свои стикеры в Телеграмме! 
        Уже догадались, о ком идёт речь? Конечно, это же:
    </span>
    <span class="gradient title">🦊 ФЕНЯ 🦊</span>
    <span class="text">
        Он же лисица фенек – 
        это маленький лис с большими ушами, 
        живущая в пустынях Северной Африки.
    </span>
    <span class="gradient title">Почему именно это животное?</span>
    <span class="text">
        Фенек очень маленькое, но довольно проворное существо. 
        Согласитесь, подходит под описание 
        студентов <span class="gradient"><a href="https://vk.com/profkom_uk_lgtu" target="_blank" rel="noreferrer">Университетского колледжа</a></span> 😉
    </span>
    <span class="gradient title">Тогда почему Феня?</span>
    <span class="text">
        Всё просто – студенты сами выбрали ему такое имя. 
        В 2020 году прошёл конкурс на лучший вариант имени этому зверьку. 
        Кем он только ни был:
    </span>
    <span class="gradient title">Фундук, Фенук, Финя...</span>
    <span class="gradient title">Витя Алтухов...</span>
    <span class="text">
        Можно перечислять до бесконечности. 
        Но всё же остановились на варианте <a href="https://vk.com/nastrout" target="_blank" rel="noreferrer">Анастасии Пановой</a>, 
        которая и предложила это имя, 
        которое сейчас знают все студенты колледжа 🦊
    </span>
    <span class="gradient title">Великий создатель Фени</span>
    <span class="text">
        За сам облик Фени, каким его привыкли видеть, 
        хочется поблагодарить <a href="https://vk.com/imsexrabbit" target="_blank" rel="noreferrer">Мишу Горина</a>.
        Без него не было бы и нашего главного, 
        отличительного символа!
    </span>
</div>

<style>
    a {
        position: relative;
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        cursor: pointer;
        line-height: 1;
        text-decoration: none;
        opacity: .7;
        transition: .5s ;
        margin-top: 15px;
    }

    a:hover {
        opacity: 1;
        transition: .5s ;
    }

    .gradient {
        background: linear-gradient(90deg, #FF00E5 0%, #0094FF 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
    .title {
        font-size: 5vh;
        text-align: center;
    }
    .text {
        font-size: 3vh;
        width: 80%;
    }

    .legend {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: center;
        align-content: center;
        overflow: scroll;
    }

    @media screen and (orientation:portrait) {
        .title {
            font-size: 3vh;
            text-align: center;
        }
        .text {
            font-size: 2vh;
            width: 80%;
        }
    }
</style>