# События

- `v-on:click` и `@click` это одно и тоже

## mousemove
Перемещаем мышь по заголовку, в заголовке показываются координаты мыши:

    <h2 @mousemove="foo">{{x}} {{y}} <span @mousemove.stop=""> ОТКЛЮЧИТЬ СОБЫТИЕ </span></h2>

     var app = new Vue({
        el: '#app',
        data: {
            x: 0,
            y: 0,
        },
        methods: {
            foo(e) {
                this.x = e.clientX
                this.y = e.clientY
            },
        },
    })
