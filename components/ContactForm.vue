<template>
  <form method="POST" @submit.prevent="submit">
    <input v-model="email" type="email" placeholder="Your email" class="input" required>
    <textarea v-model="message" placeholder="Your message..." class="textarea" rows="5" required />
    <input name="_formsubmit_id" type="text" style="display:none">
    <div class="text-right">
      <cta-button :disabled="sending" v-text="sending ? 'Sending...' : 'Send'" />
    </div>
  </form>
</template>

<script>
import CtaButton from '@/components/CtaButton.vue'
import axios from 'axios'

export default {
  components: {
    CtaButton
  },

  data() {
    return {
      sending: false,
      email: '',
      message: ''
    }
  },

  methods: {
    submit() {
      const url = 'https://services.lukaspapay.com/email-formsubmission'
      const { email, message } = this
      this.sending = true
      axios
        .post(url, {
          data: { email, message },
          options: { subject: "Let's work together", replyTo: email }
        })
        .then(() => {
          this.$emit('submit', { email, message })
          this.resetFormInputs()
        })
        .catch(({ response }) => console.log(response))
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
