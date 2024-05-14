<template>
    <h1>{{ text }}</h1>
    <div class="user-card">
        <h2>Научу зарабатывать от 50 000р. в час</h2>
        <div class="main-information flex">
          <img src="../assets/images/коуч.jpg" width="500px">
          <div class="info">
            <h2>
                {{ getAuthorFullName }} 
            </h2>
            <strong>Бизнес-коуч</strong>
            <ul class="list">
              <li>Учу делать РЕАЛЬНЫЕ бабки, на себя просто не хватило времени</li>
              <li>НЕ знаю, что такое "Успешный Успех", но знаю, что нужно ТЕБЕ!</li>
              <li>Пообещал, что побреюсь, когда кого-нибудь ОБМАНУ.</li>
            </ul>
          </div>
        </div>
        <p>Участников: {{ users.length }}</p>
        <ul>
          <li 
            v-for="(user, index) in users"
            :key="index"
          >
            {{ `${index + 1} ${getFullName(user)}` }}
          </li>
        </ul>
        <p>Еще один список для прохода по свойствам объекта {{ getFullName(users[0]) }}</p>
        <ul>
          <li 
            v-for="(value, key, index) in users[0]"
            :key="index"
          >
            {{ `${key} - ${value}` }} 
          </li>
        </ul>
        <div>
          <button 
            type="button"
            @click="currentPage--"
          >
            Предыдущая
          </button>
          <button 
            type="button"
            v-for="page in pages"
            :key="page"
            @click="currentPage = page"
          >
            {{ page }}
          </button>
          <button
            type="button"
            @click="currentPage++"
          >
            Следующая
          </button>
          <p>Страница {{ currentPage }} из {{ pages }}</p>
        </div>
    </div>
</template>
  
<script>
  export default {
    name: 'UserCard',
    data() {
        return {
            text: 'Hello from 14.05.2024', 
            firstName: 'Игнатий',
            secondName: 'Илларионович',
            lastName: 'Богатов',
            users: [
              {
                firstName: 'Иван',
                secondName: 'Иванович',
                lastName: 'Иванов'
              },
              {
                firstName: 'Андрей',
                secondName: 'Андреевич',
                lastName: 'Андреев'
              },
              {
                firstName: 'Петр',
                secondName: 'Петрович',
                lastName: 'Петров'
              }
            ],
            pages: 3,
            currentPage: 1
        }
    },
    computed: {
        getAuthorFullName() {
            return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
        }
    },
    methods: {
      getFullName(user) {
        return `${user.firstName} ${user.secondName} ${user.lastName}`
      },
      loadUsers(page) {
        console.log(`Загрузка пользователей: страница ${page}`)
      }
    },
    watch: {
      currentPage(page) {
        this.loadUsers(page)
      }
    } 
  }
</script>
  
<style>
    .user-card {
      margin-top: 40px;
    }
    .info {
      margin-left: 50px;
    }
    h2 {
      margin-bottom: 14px;
    }
</style>
  