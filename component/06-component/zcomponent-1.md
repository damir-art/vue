# Component
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
