# Component
Компоненты это сущность которую можно использовать повторно. Обычно большое приложение делят на маленькие кусочки (компоненты), чтобы его было удобней поддерживать.

- Компонент помещают над инициализацией vue-приложения
- Компонент содержит в себе HTML-код элемента страницы, например карточки товара

Код:

    // Вывод компонента (дочерний)
    <card></card>
    <card></card>
    <card></card>
    
    // Создание компонента (родитель)
    Vue.component('card', {
        template: `
            <div>
                <h3>Название товара #код</h3>
                <button type="button">Купить</button>
            </div>
        `
    })

## Передаём данные от родителя к дочернему
Передаём данные от родителя к дочернему компоненту:

    // Создание компонента (родитель)
    Vue.component('card', {
        template: `
            <div>
                <h3>Название товара #код</h3>
                <button type="button">Купить</button>
            </div>
        `
    })
