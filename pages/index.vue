<template>
  <div>
    <h1> ff</h1>
    <h1> Test </h1>
    <!--    <p>{{ post.description }}</p>-->
  </div>
</template>

<script>
// https://stackoverflow.com/questions/64950770/add-axios-authorization-on-nuxt-config
// import $axios from 'core-js/internals/queue'

export default {
  async mounted () {
    console.log(1111111)
    const webApiUrl = 'ttps://api.ukrainealarm.com/api/v3/alerts'
    const tokenStr = '9837f384:99a575fc7d6e0ad4b8b96d11cc2829a3'
    const res = await this.$axios.$get(webApiUrl, {
      headers: {
        Authorization: `Bearer ${tokenStr}`,
        'Access-Control-Allow-Origin': '*',
        'Content-Type': 'application/json'
      }
    })
    console.log(res)

    // const config = {
    //   headers: {
    //     'Content-Type': 'application/json',
    //     'Access-Control-Allow-Origin': '*',
    //     Authorization: '9837f384:99a575fc7d6e0ad4b8b96d11cc2829a3'
    //   }
    // }

    // let data = ''

    // await this.axios.get('http://196.121.147.69:9777/twirp/route.FRoute/GetLists', config)
    //   .then((res) => {
    //     // console.log(res)
    //     data = 'res'
    //   })
    //   .catch((err) => {
    //     // console.log(err)
    //   })
    // }

    // const source = this.$axios.CancelToken.source()
    // this.$axios.setHeader('accept', 'application/json')
    // this.$axios.setHeader('Access-Control-Allow-Origin', '*')
    // this.$axios.setHeader('Authorization', '9837f384:99a575fc7d6e0ad4b8b96d11cc2829a3')
    // const ip = await this.$axios.$get('https://api.ukrainealarm.com/api/v3/alerts', config)
    // console.log(ip)

    // await this.$axios.$get('https://jsonplaceholder.typicode.com/todos/1', {
    //   cancelToken: source.token
    // }).catch((error) => {
    //   if (this.$axios.isCancel(error)) {
    //     console.log('Request canceled', error)
    //   } else {
    //     // handle error
    //   }
    // })

    // this.$axios.$post('/user/12345', {
    //   name: 'new name'
    // }, {
    //   cancelToken: source.token
    // })

    // cancel the request (the message parameter is optional)
    // source.cancel('Operation canceled by the user.')
    // // console.log(this.asyncData())
    // const data = (await $axios.get('http://icanhazip.com')).data
    // console.log(data)
  },
  methods: {
    // async asyncData ({ $axios }) {
    //   const ip = await $axios.$get('http://icanhazip.com')
    //   return { ip }
    // }
  }
}
</script>
