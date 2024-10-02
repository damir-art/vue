# Методы
Благодаря методам мы мжем сделать отдельную функцию которую вызовем по наступлении события.  
Методы могут принимать event, `addNumber(evt) {}`.  
При вызове методов можно также добавлять аргументы: `addNumber(arg, arg2, arg3)`.  
Минусы методов и почему их заменяют вычисляемыми свойствами, читай в `begin/computed.md`

- Добавим числа в список рандомно от -5 до 5 и выведем их `Пример №1`. 
- Выведем сумму этих чисел `Пример №2`.

## Пример №1
По клику добавим рандомные числа в список рандомно от -5 до 5 и выведем их:

    <div class="container">
      <div class="sample">
        <button v-on:click="addNumber">Добавить</button>
        <ul>
          <li v-for="number in numbers">{{ number }}</li>
        </ul>
      </div> <!-- sample -->
    </div>

    <script>
    let sample = Vue.createApp({
      data() {
        return {
          numbers: []
        }
      },

      // Методы создаём в объекте methods
      methods: {
        // добавляем в список рандомные числа
        addNumber() {
          this.numbers.push(Math.random());
        }
      }
    }).mount('.sample');
    </script>

Рандомные числа от -5 до 5:

    addNumber() {
      let rnd = Math.floor(Math.random() * 11) - 5;
      this.numbers.push(rnd);
      console.log(this.numbers);
    }

Код выше использует функцию Math.random() для генерации случайного числа от 0 до 1, затем умножает его на 11 (чтобы получить диапазон от 0 до 11), после чего округляет полученное число вниз до ближайшего целого с помощью Math.floor() и вычитает 5, чтобы получить желаемый диапазон от -5 до +5.

## Пример №2
Выведем сумму этих чисел.

    <div class="sample">
      <button v-on:click="addNumber">Добавить</button>
      <h3>Сумма чисел: {{ sum() }}</h3>
      <ul>
        <li v-for="number in numbers">{{ number }}</li>
      </ul>
    </div> <!-- sample -->

    <script>
    let sample = Vue.createApp({
      data() {
        return {
          numbers: []
        }
      },

      methods: {
        addNumber(evt) {
          let rnd = Math.floor(Math.random() * 11) - 5;
          this.numbers.push(rnd);
          console.log(evt.target);
        },
        sum() {
          let sum = 0;
          for(let i = 0; i < this.numbers.length; i++) {
            sum += this.numbers[i];
          }
          return sum;
        }
      }
    }).mount('.sample');
    </script>

Вставляя числа в список видим реактивные изменения подсчета суммы чисел.

# Старая запись
`data` статична, методы придают ей динамики:

    methods: {
        greet: function () {
            return 'Hello my name is ' + this.name
        },
        upperCase: function() {
            return this.name.toUpperCase()
        }
    }

- methods - свойство, объект в котором хранятся методы
- greet - имя метода, ключ объекта
- function - тело функции, значение метода

## Вызов метода

    {{ greet() }}

## Реактивность Vue.js
Изменение информации внутри модели (data), мгновенно изменяет шабон (id="app").
