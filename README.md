# Slider-on-native-Js


## Описание

Простой слайдер на нативном Javascript.

- Неограниченное количество слайдов
- Бесконечная прокрутка
- Счетчик слайдов: общее количество / номер активного слайда
- Перемещение через - "Arrows", "Dots"



## Подключение

1) Без сборщика модулей, подключаем к Html файлу перед основным JS файлом

```
<script type="module" src="js/slider.js"></script>
<script type="module" src="js/main.js"></script>
```

slider.js - подключаемый слайдер
main.js   - ваш скриптовый файл

В main.js импортируем слайдер:

```
import slider from './slider.js';
```
Добавить slaider.css файл в <head> (можно подключить свои стили в зависимости от HTML разметки)
  
  

2)  Со сборщиком модулей, копируем файл в папку с модулями для дальнейшего объединения с помощью сборщика модулей
затем импортируем:
```
import slider from './slider.js';
```
Добавить slaider.css файл в <head> (можно подключить свои стили в зависимости от HTML разметки)



## Настройка слайдера

Нужно настроить разметку HTML (разметку можно менять, не нужные блоки убирать - если классы изменятся то нужно будет исправить их при вызове функции в JS файле):

```
  <div class="offer">
        <div class="container">
            <div class="offer__slider">                                         //обертка слайдера(блок в который обварачивается блок счетчика, Btn и картинок слайдера)
                <div class="offer__slider-counter">
                    <div class="offer__slider-prev">                            //кнопка переключения предыдущего слайдера
                        <img src="img/icons/left.svg" alt="prev">               //картинка стрелки переключения предыдущего слайдера
                    </div>
                    <span id="current">03</span>                                //отображение номера текущего слайда
                    /
                    <span id="total">04</span>                                  //отображение общего количество слайдов
                    <div class="offer__slider-next">                            //кнопка переключения следующего слайдера
                        <img src="img/icons/right.svg" alt="next">              //картинка стрелки переключения следующего слайдера
                    </div>
                </div>
                <div class="offer__slider-wrapper">                             //обертка для карусели (прячет не активные слайды)
                  <div class="offer__slider-inner">                             //обертка слайдов
                    <div class="offer__slide">                                  //блок в котором находиться изображение слайдера
                        <img src="img/slider/pepper.jpg" alt="pepper">          //слайд №1
                    </div>
                    <div class="offer__slide">                                  //блок в котором находиться изображение слайдера
                        <img src="img/slider/food-12.jpg" alt="food">           //слайд №2
                    </div>
                    <div class="offer__slide">
                        <img src="img/slider/olive-oil.jpg" alt="oil">          //слайд №3
                    </div>
                    <div class="offer__slide">
                        <img src="img/slider/paprika.jpg" alt="paprika">        //слайд №4
                    </div>
                  </div>
                </div>
            </div>
        </div>
    </div>
```



## Запуск слайдера

После импорта функции slider из slider.js, вызываем функцию с заданными классами(классы можно задать в зависимости от своей HTML разметки):

slider({
    container: '.offer__slider',
    nextArrow: '.offer__slider-next',
    prevArrow: '.offer__slider-prev',
    slide: '.offer__slide',
    totalCounter: '#total',
    currentCounter: '#current',
    wrapper: '.offer__slider-wrapper',
    field: '.offer__slider-inner'
});



## Описание инпутов слайдера

- .container: - обертка слайдера(блок в который обварачивается блок счетчика, Btn и картинок слайдера)
- .nextArrow  - кнопка переключения следующего слайдера
- .prevArrow  - кнопка переключения предыдущего слайдера
- .slide - блок в котором находиться изображение слайдера
- .totalCounter - блок в котором будет отображаться общее количество слайдов
- .currentCounter - блок в котором будет отображаться номер текущего слайда
- .wrapper - обертка для field (прячет не активные слайды)
- .field - обертка слайдов(обварачивает обертки изображении - .slide)



## Демо

https://kainar9292.github.io/slider-on-native-Js/
