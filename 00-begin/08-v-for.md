# Директива v-for
v-for директива для отображения списков.

    <ul v-for="f in loop">
        <li>{{ f.ind }}</li>
    </ul>

    var app = new Vue({
        el: '#app',
        data: {
            loop: [
                { ind: 'element 1' },
                { ind: 'element 2' },
                { ind: 'element 3' },
            ]
        }
    })
