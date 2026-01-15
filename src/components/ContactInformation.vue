<script setup>
import Icon from "@/components/Icon.vue";
</script>

<template>
  <div class="info-side">
    <h3>Contact Information</h3>
    <ul class="info-list">
      <li>
        <Icon
            icon="/icons/mail.svg"
            alt="Mail icon"
        />
        <div>
          <strong>Email</strong>
          <p>fixrightpropertyservices26@gmail.com</p>
        </div>
      </li>
      <li>
        <Icon
            icon="/icons/phone.svg"
            alt="Phone icon"
        />
        <div>
          <strong>Phone</strong>
          <p>+353 00 000 0000</p>
        </div>
      </li>
      <li>
        <Icon
            icon="/icons/location.svg"
            alt="Location icon"
        />
        <div>
          <strong>Address</strong>
          <p>123 Random Street,<br>Co. Mayo, Ireland</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.info-side { flex: 1; }
.info-list { list-style: none; margin-top: 1.5rem; }

.info-list li {
  display: flex;
  gap: 1rem;
  margin-bottom: 1.5rem;
}
.info-list strong { display: block; font-size: 0.9rem; }
.info-list p { font-size: 0.9rem; color: var(--color-text-light); }

</style>