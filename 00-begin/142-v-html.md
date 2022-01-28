# v-html (сырой html)
Директива позволяет вставить HTML-код в шаблон. Не рекомендуется использовать для данных которые получены из вне (от пользователя), например комментарий от посетителя сайта.

    <div v-html="text"></div> // text: вставится как HTML-код
    <div>{{ text }}</div>     // text: вставится в текстовом формате

    data: {
        text: '<p>Супер <b>текст</b></p>'
    }