# array
Работаем с массивами ициклами.

    <ul>
        <li v-for="people in peoples"> {{ people.name }} {{ people.surname }} {{ people.age }} </li>
    </ul>

    data: {
        peoples: [
            {
                name: 'Иван',
                surname: 'Иванов',
                age: 25,
                job: true
            },
            {
                name: 'Петр',
                surname: 'Петров',
                age: 30,
                job: false
            },
            {
                name: 'Сидор',
                surname: 'Сидоров',
                age: 35,
                job: true
            }
        ]
    }

## v-bind:class
Динамически добавляет классы к элементам по условию.

    .strike {
        text-decoration: line-through;
    }

Зачеркнутся все люди у которых есть работа:

    <li v-bind:class="{'strike': people.job}">

Зачеркнутся все люди у которых нет работы:

    <li v-bind:class="{'strike': !people.job}">
