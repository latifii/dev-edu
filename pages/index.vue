<template>
  <div>Home</div>
  <article class="prose">
    <h1>عنوان مقاله</h1>
    <p>
      این یک پاراگراف است که به طور خودکار استایل‌های تایپوگرافی اعمال خواهد
      شد...
    </p>
    <p>
      متن‌های طولانی، لینک‌ها، تصاویر و جدول‌ها نیز به طور خودکار استایل‌های
      زیبایی دریافت می‌کنند.
    </p>
  </article>
  <input v-model="email" v-bind="emailAttrs" />

  <pre>values: {{ values }}</pre>
  <pre>errors: {{ errors }}</pre>
</template>

<script setup lang="ts">
import { Form, useForm } from "vee-validate";
import * as yup from "yup";
const { values, errors, defineField } = useForm({
  validationSchema: yup.object({
    email: yup.string().email().required(),
  }),
});

const [email, emailAttrs] = defineField("email");
</script>

<style scoped></style>
