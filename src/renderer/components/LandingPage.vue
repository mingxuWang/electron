<template>
  <div id="wrapper">
    <main>
      <div class="left-side">
        <el-button type="info" @click="changeAudio" plain>语音播报</el-button>
        <voice :message="msg"></voice>
        <system-information></system-information>
      </div>
    </main>
  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation'
  import Voice from './voice/voice'
  export default {
    name: 'landing-page',
    components: {
      SystemInformation,
      Voice
    },
    data () {
      return {
        baseUrl: 'http://10.93.109.31:8002/tts?idx=1&cuid=speech&lan=zh&ctp=1&pdt=1&tex=',
        key: '您有新的滴滴外卖订单，请及时处理',
        num: 0,
        msg: '',
        value2: true
      }
    },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      },
      changeAudio () {
        this.num++
        this.msg = '您有新的滴滴外卖订单，请及时处理' + this.num
      }
    },
    created () {
      this.$message({
        message: '警告哦，这是一条警告消息',
        type: 'warning'
      })
    }
  }
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }


  #wrapper {
    width: 100%;
  }

  main {
    display: flex;
    justify-content: space-between;
  }


  .left-side {
    width: 50%;
    display: flex;
    flex-direction: column;
  }
  .right-side {
    width: 50%;
    display: flex;
    flex-direction: column;
  }

  .welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
  }

  .title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: black;
    margin-bottom: 10px;
  }

  .doc button {
    font-size: .8em;
    cursor: pointer;
    outline: none;
    padding: 0.75em 2em;
    border-radius: 2em;
    display: inline-block;
    color: #fff;
    background-color: #4fc08d;
    transition: all 0.15s ease;
    box-sizing: border-box;
    border: 1px solid #4fc08d;
  }

  .doc button.alt {
    color: #42b983;
    background-color: transparent;
  }
</style>
