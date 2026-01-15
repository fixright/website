<script setup>
import { ref } from 'vue';
import BaseButton from "@/components/BaseButton.vue";

const name = ref('');
const email = ref('');
const message = ref('');

const sendEmail = () => {
  const destinationEmail = "fixrightpropertyservices26@gmail.com";

  const subject = `New Inquiry from ${name.value}`;

  const body = `Name: ${name.value}\nEmail: ${email.value}\nMessage:\n${message.value}\n`;
  window.location.href = `mailto:${destinationEmail}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
};
</script>

<template>
  <div class="form-side">
    <form @submit.prevent="sendEmail">
      <div class="field">
        <label>Name</label>
        <input v-model="name" type="text" placeholder="Your name" required />
      </div>
      <div class="field">
        <label>Email</label>
        <input v-model="email" type="email" placeholder="Your email" required />
      </div>
      <div class="field">
        <label>Message</label>
        <textarea v-model="message" placeholder="Tell us about the service you would like to get" required></textarea>
      </div>
      <BaseButton class="submit-btn" variant="primary" type="submit">Send Message</BaseButton>
    </form>
  </div>
</template>

<style scoped>
.form-side { flex: 1.5; }
.field { margin-bottom: 1rem; }
.field label {
  display: block;
  font-size: 0.8rem;
  font-weight: 600;
  margin-bottom: 0.3rem;
}
.field input, .field textarea {
  width: 100%;
  padding: 0.6rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  background: #f4f4f4;
}
.field textarea { height: 100px; resize: vertical; }
.submit-btn { width: 100%; }
</style>