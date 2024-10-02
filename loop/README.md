# Цикл
Изучаем перебор массивов и объектов циклом `v-for`.

- Работа с массивами - `array.md`
- Работа с объектами - `object.md`
- Работа с JSON - `json.md`

Пример с v-for:

    <div class="sample">
      <ul>
        <li v-for="number in numbers">{{ number }}</li>
      </ul>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          numbers: [1, 2, 3]
        }
      }
    }).mount('.sample');

Добавляем в массив рандомные числа, которые выводятся в списке:

    <div class="sample">
      <button v-on:click="numbers.push(Math.random())">Добавить</button>
      <ul>
        <li v-for="number in numbers">{{ number }}</li>
      </ul>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          numbers: []
        }
      }
    }).mount('.sample');