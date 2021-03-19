# Обработка событий клавиатуры
- `@keyup.enter = "addPost"` событие произойдёт при нажатии на `enter`

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