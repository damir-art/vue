# Модификаторы событий
Существует три стадии прохода события:
- событие идет сверху вниз (перехват)
- событие достигает целевого элемента (таргет)
- событие идет снизу вверх (всплытие)

Аналоги .preventDefault(), .stopPropagation() на Vue

- .stop    - отменяет дальнейшее распростарнение события
- .prevent - отменяет событие по умолчанию
- .capture - используется при делегировании
- .self    - используется при делегировании
- .once    - событие сработает 1 раз
- .passive - повышает производительность на мобильных устройствах

## prevent, stop
- `.prevent=""` .preventDefault()
- `.stop=""` .stopPropagation()

Отменяем отправку формы **@submit.prevent=""**:

    <form @submit.prevent="" action="#" method="get">
        <button type="submit">Отправить</button>
    </form>

Отменяем переход по ссылке **@click.prevent=""**:

    <a @click.prevent="" href="#">Ссылка</a>

На `span` отменяется действие **mousemove**:

    <h2 @mousemove="foo"> {{x}} {{y}} <span @mousemove.stop=""> ОТКЛЮЧИТЬ СОБЫТИЕ </span> </h2>

## prevent, stop в методах
Модификаторы событий можно вписывать не только в атрибуты HTML-тегов но и в модели.

    a(href="https://ya.ru" @click="clickLink") Link

    methods: {
        clickLink (e) {
            e.preventDefault()
            this.counter++
        }
    }

## Разное
- модификаторы можно объединять в цепочку
- модификаторы можно использовать без указания обработчика `@click.prevent`
