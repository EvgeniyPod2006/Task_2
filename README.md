# Task_2
<html>

<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css">
</head>

<body>

  <div id="app" class="ui container">
    <h1>Notification Center</h1>

    <notification-message type="error" header="Oh no!">
      <p>Your flight has been <b>canceled</b></p>
    </notification-message>

    <notification-message type="success" header="Oh yeah!">
      <p>Your flight is on time!</p>
    </notification-message>

    <notification-message>
      <p>Good morning :)</p>
    </notification-message>
  </div>

  <!-- Template for Notification Message -->
  <script type="text/x-template" id="notification-message-template">
    <!-- Notification Message Markup -->
    <!-- Types: info, warning, error, success -->
    <div class="ui message" :class="type" v-if="!hidden">
      <i class="close icon" @click="hide"></i>
      <div class="header">
        {{header}}
      </div>
      <slot></slot>
    </div>
  </script>

  <!-- Import Vue.js -->
  <script src="https://unpkg.com/vue@3"></script>

  <!-- Your JavaScript Code :) -->
  <script>
    Vue.createApp({})
    .component('notification-message', {
      template: '#notification-message-template',
      props:{
        type: {type: String, default: 'info'},
        header: {type: String, default: 'Information'}
      },
      data(){
        return {
          hidden: false
        }
      },
      methods:{
        hide(){
          this.hidden = true
        }
      }
    })
    .mount('#app')
  </script>
</body>

</html> 
