

<template>
  <section class="m-4">
    <h2 class="text-center m-4">{{message}}</h2>
    <h3>Директива v-model</h3>
    <form  action="#" method="POST">
      <input v-model="login" class="p-1" type="text" name="login" value="" placeholder="Введите логин">
      <p>Ваш логин:{{login}} </p>
    </form>

    <h3 >Директива v-if</h3>
    <div v-if="seen" class="m-4">
      <p>Этот блок виден, так как переменная seen - истина</p>
    </div>
    <div v-if="!seen" class="m-4">
      <p>Этот блок виден, так как переменная seen - ложна</p>
      <p>Он убран из DOM-дерева</p>
    </div>


    <h3>Директива v-show</h3>
    <div v-show="seen" >
      <p>Этот блок виден, так как переменная seen - истина</p>
      <p>А второй блок скрыт с помощью свойства display</p>
    </div>
    <div v-show="!seen" >
      <p>Этот блок виден, так как переменная seen - ложна</p>
      <p>К нему добавлен атрибут style="display: none; "</p>
    </div>

    <h3 >Директива v-for (Массив)</h3>
    <div>
      <p>Список фруктов:</p>
      <ol>
        <li v-for="fruit in fruits">{{ fruit }}</li>
      </ol>
    </div>

    <h3 >Директива v-for (Массив) объектов</h3>
    <div>
      <p>Список студентов:</p>
      <ol>
        <li v-for="student in students">
          ФИО:<b> {{student.fio}}</b> <br />
          Дата рождения: {{student.birth}} <br />
          Пол: {{student.sex}} <br />
        </li>
      </ol>
    </div>

    <h3>Директива v-bind</h3>
    <div>
      <img v-bind:src="bind_img" alt="Картинка" width="300">
      <br />
      <input type="text" v-bind:value="bind_value" disabled>
    </div>

    <h3>Директива v-on</h3>
    <div>
      <button v-on:click="click_green" class="btn btn-success">Кнопка 1</button>
      <button @click="click_red" class="btn btn-danger m-1">Кнопка 2</button>
    </div>

  </section>

</template>

<script >
  export default {
    data(){
      return{
        message: 'Приветствую вам на курсе по изучению фреймворка на Vue 3!',
        login: null,
        seen:true,
        fruits: ["Яблоко","Апельсин", "Банан", "Груша","Папайя"],
        students: [{
          fio: 'Евсеев Дмитрий Витальевич',
          birth: '04.11.2005',
          sex: 'мужской'
        },
          {
            fio: 'Буйкин Андрей Анатольевич',
            birth: '20.12.2005',
            sex: 'мужской'
        },
          {
            fio: 'Шейкина Елизовета Викторовна',
            birth: '23.04.2005',
            sex: 'женский'
          },
        ],
        bind_img: "https://i.pinimg.com/originals/cb/f1/6a/cbf16abef328a6aea62808a64d010d2d.jpg",
        bind_value: "Милый жираф",
      }
    },
    //Методы
    methods:{
      click_green(){
        alert("Вы нажали зелёную кнопку");
      },
      click_red(){
        alert("Вы нажали красную кнопку");
      },
    }
  }
</script>