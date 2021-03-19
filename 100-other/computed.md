# Computed
Вычисляемое свойство

Рассмотрим пример с счетчиком и будем менять подзаголовок в зависимости от числа счетчика.

    <div id="app">
        <h2>{{ subTitleСomputed }}</h2>

        <p class="out">
            {{ paragraph }}
        </p>

        <button type="button" @click="paragraph++">Кнопка +1</button>
        <button type="button" @click="paragraph--">Кнопка -1</button>
    </div>

    const app = new Vue({
        el: '#app',
        data: {
            subTitle: 'Подзаголовок приложения',
            paragraph: 0,
        },
        computed: {
            subTitleСomputed() {
                return this.paragraph > 3 ? 'Больше 3' : 'Mеньше 3'
            }
        }
    })

- Название свойства и метода не должны совпадать
- `computed` это свойство которое постоянно вычисляется, поэтому свойство `paragraph` в `data` можно не записывать
- `computed` используется при динамических вычислениях