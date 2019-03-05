<template>
  <form method="POST" action="https://formsubmit.io/send/a7dcacbb-fed1-40f9-a583-c330fe4e2d46" @submit.prevent="submit">
    <input v-model="email" type="email" placeholder="Your email" class="input">
    <textarea v-model="message" placeholder="Your message..." class="textarea" rows="5" />
    <input name="_formsubmit_id" type="text" style="display:none">
    <div class="text-right">
      <cta-button>
        Send
      </cta-button>
    </div>
  </form>
</template>

<script>
import CtaButton from '@/components/CtaButton.vue'
// import axios from 'axios'

export default {
  components: {
    CtaButton
  },

  data() {
    return {
      email: '',
      message: ''
    }
  },

  methods: {
    submit() {
      // TODO: point it to my form submission url
      // const url = 'https://goo.gl/forms/YNVPJ9uLDmvgM6Rg1'
      const { email, message } = this
      // axios
      //   .post(url, { email, message })
      //   .then(() => {
      //     this.resetFormInputs()
      //   })
      //   .catch(error => console.error(error))
      this.$emit('submit', { email, message })
    },
    resetFormInputs() {
      this.email = ''
      this.message = ''
    }
  }
}
</script>

<style scoped>
.input,
.textarea {
  margin: 10px 0;
}

.input,
.textarea {
  padding: 15px 12px;
  width: 100%;
  display: block;
  border-radius: 8px;
  border: 1px solid #045cb8;
  outline: none;
  font-size: 1rem;
  font-family: 'Courier New', Courier, monospace;
}

.textarea {
  resize: none;
}

.text-right {
  text-align: right;
}
</style>
