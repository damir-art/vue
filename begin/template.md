# template
Подведем итог начальному курсу и разберёмся как data, method, computed используются в шаблоне и вью понимает что и когда использовать какую переменную, оъект, метод или computed использовать и не путается, даже когда там есть или нет скобок.

    <div class="sample">
      <button v-on:click="show = !show">
        {{ btnText }}
      </button><br />
      <h3 v-show="show">Сумма чисел: {{ sum }}</h3>
      <button v-on:click="addNumber">Добавить</button>
      <ul>
        <li v-for="number in numbers">{{ number }}</li>
      </ul>
    </div> <!-- sample -->

    let sample = Vue.createApp({
      data() {
        return {
          show: true,
          numbers: []
        }
      },

      methods: {
        addNumber(evt) {
          let rnd = Math.floor(Math.random() * 11) - 5;
          this.numbers.push(rnd);
        },
      },

      computed: {
        sum() {
          console.log(1);
          let sum = 0;
          for(let i = 0; i < this.numbers.length; i++) {
            sum += this.numbers[i];
          }
          return sum;
        },
        btnText() {
          return this.show ? 'Скрыть' : 'Показать';
        }
      }
    }).mount('.sample');

Пишем в консоли имя приложения `sample`. В Фаерфокс раскроем прокси и таргет, снизу есть:

    addNumber: BoundFunctionObject { }
    btnText: "Скрыть"​​
    numbers: Array []
    show: true
    sum: 0

Когда запустился конструктор класса Вью скопировал ключи из data, method, computed в объект sample. Таже он на них поставил геттеры и сеттеры, которые обеспечивают нам реактивность данных. Это же позволяем писать в шаблоне ключи из data, method, computed, а Вью уже сам разбирается в каком они объекте (data, method, computed) изначально были и что значат.

Это накладывает некоторые ограничения, например нельзя одновременно использовать ключи в data и methods. Это приведет к перезатиранию одного ключа другим.
