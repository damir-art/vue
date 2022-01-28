# События клавиатуры
Чтобы события срабатывали при нажатии клавиш, нужно элементу назначить событие, а в модели прописать метод обрабатывающий данное событие.

- `v-on:keyup = "pressKeyboard"`
- `@keyup = "pressKeyboard"`

Пример, выведем в консоли надпись, при нажатии клавиши на клавиатуре на текстовом поле `input`:

    input(type="text" v-on:keyup = "pressKeyboard") 

    pressKeyboard () {
        console.log('Нажали клавишу')
    }

Методы можно запускать и при нажатии определённой клавиши, например `Enter`.

- `v-on:keyup.enter = "pressKeyboard"` событие произойдёт при нажатии на `enter`
- `@keyup.enter = "pressKeyboard"` событие произойдёт при нажатии на `enter`

Пример, выведем в консоли надпись, при нажатии кнопки `Enter` на текстовом поле `input`:

    input(type="text" v-on:keyup.enter = "pressKeyboard") 

    pressKeyboard () {
        console.log('Нажали Энтер')
    }

Пример:

    <div id="app">
        <textarea @keyup.enter = "addPost" @keyup.delete = "clearInput"
            v-model="inputWall" placeholder="Стена" name="" id="" cols="30" rows="10"></textarea>

        <ul>
            <li v-for="(post, index) in posts" :key="index">
                {{ post }}
            </li>
        </ul>
    </div>

    <script src="js/vue.js"></script>

    <script>
        const app = new Vue({
            el: '#app',
            data: {
                posts: [],
                inputWall: ''
            },
            methods: {
                addPost() {
                    this.posts.push(this.inputWall)
                    // this.inputWall = '' // очищаем через эту инструкцию или используем @keyup.delete
                },
                clearInput() {
                    this.inputWall = ''
                }
            }
        })
    </script>