# Директива v-if
Директива `v-if` показывает или скрывает элемент, в зависимости от значения `true/false`

    <div v-if="show">
            
    </div>

    var app = new Vue({
        el: '#app',
        data: {
            show: true // false
        }
    })
