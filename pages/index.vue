<template>
  <div class="container">
    <!--{{ users[0].id }} , {{ users[0].name }}-->
    <ul>
      <!-- json配列の「id」、「name」、「companyname」を表示 -->
      <li v-for="user in users" :key="user.id">
        {{user.id}} , {{user.name}}, {{user.company.name}}
      </li>
    </ul>
  </div>
</template>

<script>
const axios = require('axios')
let url = 'https://jsonplaceholder.typicode.com/users'

export default {
    asyncData({}){
        return axios.get(url)
        .then((res) => {
            return{users: res.data}
        })
    }
}
</script>
