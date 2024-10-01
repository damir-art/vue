# Пример Options API
Пример создания компонента с помощью Options API

    export default {
      data() {
        return {
          name: '',
          age: 0,
          aboveAge: false
        };
      },
      computed: {
        displayProfile() {
          return `My name is ${this.name} and I am ${this.age}`;
        }
      },
      methods: {
        verifyUser() {
          if (this.age < 18) {
            this.aboveAge = false;
          } else {
            this.aboveAge = true;
          }
        }
      },
      mounted() {
        console.log('Application mounted');
      }
    };
