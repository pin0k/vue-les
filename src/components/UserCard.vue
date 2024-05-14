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
        <p>Участников: 0</p>
        <ul>
          <li></li>
        </ul>
    </div>
</template>
  
<script>
    export default {
        name: 'UserCard',
        data() {
            return {
                text: 'Hello from 14.05.2024', 
                firstName: 'Игнатий',
                secondName: 'Иларионович',
                lastName: 'Богатов'
            }
        },
        computed: {
            getAuthorFullName() {
                return this.firstName.toUpperCase() + ' ' + this.secondName.toUpperCase() + ' ' + this.lastName.toUpperCase()
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
  