<template>
  <div id="app">
    <h1>Telephone Input Vue</h1>
    <h2 style="color: #999">made with &#x2764; by Steven.</h2>
    <div style="width: 500px; margin: 20px auto;">
      <vue-tel-input v-model="phoneNumber" @onInput="onInput" :preferredCountries="['us', 'gb', 'ua']"></vue-tel-input>
    </div>
    <div v-if="phone.number" style="color: #e83e8c">
      <span>
        Number:
        <strong>{{ phone.number }}</strong>,&nbsp;
      </span>
      <span>
        National:
        <strong>{{ phone.national }}</strong>,&nbsp;
      </span>
      <span>
        Is valid:
        <strong>{{ phone.isValid }}</strong>,&nbsp;
      </span>
      <span>
        Country:
        <strong>{{ phone.country }}</strong>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      phoneNumber: "+84963077599",
      phone: {
        number: '',
        isValid: false,
        country: undefined,
      },
    };
  },
  methods: {
    onInput({ number, national, isValid, country }) {
      this.phone.number = number;
      this.phone.national = national;
      this.phone.isValid = isValid;
      this.phone.country = country && country.name;
    },
  },
};
</script>
