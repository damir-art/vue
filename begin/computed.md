# computed (вычисляемые свойства)
Вычисляемые свойства (computed properties) в Vue.js используются для динамического вычисления значений на основе данных, хранящихся в компоненте. Они позволяют создавать сложные выражения и функции, которые автоматически пересчитываются при изменении зависимостей. Это делает их полезными для представления производных данных, таких как суммы, средние значения, или форматирование дат.

Пример использования вычисляемых свойств:

    <template>
      <p>Имя: {{ name }}</p>
      <p>Фамилия: {{ surname }}</p>
      <p>Полное имя: {{ fullName }}</p>
    </template>

    <script>
    export default {
      data() {
        return {
          name: 'Иван',
          surname: 'Иванов',
        };
      },
      computed: {
        fullName() {
          return `${this.name} ${this.surname}`;
        },
      },
    };
    </script>

В этом примере мы используем вычисляемое свойство fullName для объединения имени и фамилии в полное имя. Когда данные name или surname изменяются, fullName автоматически пересчитывается без необходимости явного вызова метода.

Пример берем из `begin/method.md`  
Добавляем кнопку показа / скрытия заголовка, где выводится сумма подсчета.  
Дописываем в метод sum(): console.log(1).  
console.log(1) срабатывает как при подсчете суммы, так и при скрытии заголовка.  
Это не правильно с тчоки зрения производительности.  
Сумма будет пересчитываться даже если поставить v-show="show" не h2, а другому элементу.  
Поэтому в этом случае используем не методы, а `computed`.  
Переносим функцию `sum()` из method в computed.  
Убираем в template, у функции `sum` скобки.

    <div class="sample">
      <button v-on:click="show = !show">Показать</button><br />
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
        }
      }
    }).mount('.sample');

Методы плохо себя проявляют, когда происходят не в какой-то момент времени, а когда пытаемся вызвать их в шаблоне. Не важно какая часть вью обновится, метод всё равно будет вызван заного и это не оптимально.

computed записываются также как и методы, с синтаксической точки зрения. Их смысл заключается в том что это поля которые зависят от других полей. Например sum() будет обновляться только тогда, когда будут обновляться те элементы на которые sum() завязан, например: numbers[].

Вычисляемые свойства применяются очень часто. Например вынесем туда тернарный оператор из `directive/v-show.md`

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
