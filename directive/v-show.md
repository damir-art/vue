# v-show
v-show - одна из самых простых директив

Директива `v-show` во Vue.js используется для управления видимостью элементов в зависимости от условий, определённых в модели Vue.js. Значением может быть true/false, операция возвращающая true/false или ссылка на метод. Также можно записать тернарный оператор (любую однострочную инструкцию?).

В отличие от v-if, которая добавляет или удаляет элементы из DOM в зависимости от условия, v-show всегда оставляет элемент в DOM, но управляет его видимостью через CSS свойство display. Это делает v-show более эффективным с точки зрения производительности, особенно при работе с большими наборами данных или анимациями, где частые добавления и удаления элементов могут замедлять работу приложения.

Основной синтаксис использования v-show следующий:

    <div v-show="true/false">...</div>
    <div v-show="condition">...</div>

Элемент с v-show будет отображаться только тогда, когда условие condition истинно. Если condition ложно, элемент будет скрыт, но останется в DOM.

Пример использования v-show для отображения кнопки "Показать больше" в зависимости от длины массива товаров:

    <button v-show="products.length > 5" class="btn btn-primary">Показать больше</button>

В этом примере кнопка "Показать больше" будет видна только тогда, когда длина массива products больше 5. Это позволяет пользователю увидеть дополнительные товары, если они доступны.

Важно отметить, что v-show работает лучше всего с элементами, которые имеют начальное состояние скрытия (например, display: none в CSS), поскольку добавление и удаление элементов из DOM может привести к нежелательным эффектам анимации и производительности.

## Значение в data

    <div class="sample">
      <h2 v-show="showH2">Заголовок</h2>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          showH2: true
        }
      }
    }).mount('.sample');

## Скрываем заголовок по нажатию по кнопке

    <div class="sample">
      <button v-on:click="showH2 = !showH2">Показать скрыть</button>
      <h2 v-show="showH2">Заголовок</h2>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          showH2: true
        }
      }
    }).mount('.sample');

`v-on:click="showH2 = !showH2"` - при клике по кнопке, запишем в переменную showH2 значение наоборот.  
`v-on:click="showH2 = hello"` - введем в консоли sample.showH2 получим значение hello.

## Добавляем v-bind
При наведении на кнопку title покажет true или false.

    <button
      v-on:click="showH2 = !showH2"
      v-bind:title = "showH2"
    >Показать скрыть</button>

С тернарным оператором:

    v-bind:title = "showH2 ? 'Скрыть' : 'Показать'"

## Добавляем фигурные скобки
    
    <p>
      При нажатии по кнопке, покажет true или false {{ showH2 }}.
    </p>