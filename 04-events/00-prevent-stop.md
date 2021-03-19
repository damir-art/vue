# prevent, stop
Аналоги .preventDefault(), .stopPropagation() на Vue

- `.prevent=""` .preventDefault()
- `.stop=""` .stopPropagation()

Отменяем отправку формы **@submit.prevent=""**:

    <form @submit.prevent="" action="#" method="get">
        <button type="submit">Отправить</button>
    </form>

Отменяем переход по ссылке **@click.prevent=""**:

    <a @click.prevent="" href="#">Ссылка</a>

На `span` отменяется действие **mousemove**:

    <h2 @mousemove="foo"> {{x}} {{y}} <span @mousemove.stop=""> ОТКЛЮЧИТЬ СОБЫТИЕ </span> </h2>
