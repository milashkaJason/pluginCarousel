Для того что бы подключить "sliderCarousel" необходимо подключить файл "app.carouselSlider.min.js",
 а также файл "app.carouselSlider.css".

В ваш файл index.html добавить следующую разметку: 
<section id="companies" class="companies">
    <div class="container">
        <div class="companies-wrapper">
            <div class="companies-hor">
                <div class="companies-hor-item">Content</div>
                <div class="companies-hor-item">Content</div>
                <div class="companies-hor-item">Content</div>
                <div class="companies-hor-item">Content</div>
                <div class="companies-hor-item">Content</div>
            </div>
        </div>
    </div>
</section>

Content может быть любым!

Для инициализации нужно: 
1.создать новый объект:
const carousel = new SliderCarousel({options}) ----- прописать в теге <script/> или в вашем файле ***.js
2.Выполнить инициализацию: 
carousel.init(); ----- прописать в теге <script/> или в вашем файле ***.js

В опциях можно передать:
	если несколько слайдеров и они будут разные, то main и wrap должны отличаться!!!
	numberSlider: 2, -----необходимо если два и более слайдеров!!(по умолчанию 0) (номер слайдера в проекте(уникальный для каждого слайдера))
        main: '.companies-wrapper', -----необходимо!!('строка') (класс обертки слайдера)
        wrap: '.companies-hor', -----необходимо!!('строка') (класс обертки слайдов)
        showToSlides: 3, -----количество слайдов для показа(число)
        position: 0, ----- номер слайда с которого начать показ(число)(0 - первый слайд)
        infinity: true, ----- бесконечность(булевое значение true или false)
        responsive: [ ----- адаптивность
            {
                breakPoint: 1024,  -----разрешение на котором необходимо поменять количество слайдов для показа
                slideToShow: 3 -----количество слайдов которое нужно показывать на данном разрешении
            },
            {
                breakPoint: 768,
                slideToShow: 2
            },
            {
                breakPoint: 576,
                slideToShow: 1
            }
        ]
Пример: -------------------------------------
const carousel = new SliderCarousel({
        numberSlider: 2,
        main: '.companies-wrapper',
        wrap: '.companies-hor',
        showToSlides: 3,
        position: 0,
        infinity: true,
        responsive: [
            {
                breakPoint: 1024,
                slideToShow: 3
            },
            {
                breakPoint: 768,
                slideToShow: 2
            },
            {
                breakPoint: 576,
                slideToShow: 1
            }
        ]
    });
    carousel.init();
    ----------------------------------