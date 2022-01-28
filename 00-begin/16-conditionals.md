# Conditionals
Условный рендеринг. Рендеринг тех или иных тегов в зависимости от условия. Отображаем блоки по условию.

## v-if, v-else, v-show

    div
        button(@click="error = !error") Toggle Error {{ error }}
        button(@click="success = !success") Toggle Success {{ success }}
    div(v-if="error") Error {{ error }}
    div(v-else) Покажет если v-if вернет false
    div(v-show="success") Success {{ success }}

    data: {
        error: false,
        success: false
    }
