<template>
    <v-app id="inspire" class="pa-5">
      <v-form
        ref="form"
        v-model="valid"
        lazy-validation
      >
        <v-text-field
          v-model="name"
          :counter="50"
          :rules="nameRules"
          label="Name"
          required
        />
        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="E-mail"
          required
        />
        <v-select
          v-model="select"
          :items="items"
          :rules="[v => !!v || 'Item is required']"
          label="Item"
          required
        />
        <v-text-field
          v-model="text"
          :counter="500"
          :rules="textRules"
          label="Your message"
          required
        />
        <v-btn
          :disabled="!valid"
          color="success"
          @click="validate"
          v-text="'Submit'"
        />
        <v-btn
          color="error"
          @click="reset"
          v-text="'Clear'"
        />
      </v-form>
      <v-snackbar
        v-model="showSnack"
        color="success"
        top
        :timeout="2000"
      >
        Sent!
      </v-snackbar>
    </v-app>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    showSnack: false,
    name: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 50) || 'Name must be less than 50 characters'
    ],
    textRules: [
      v => !!v || 'Message is required',
      v => (v && v.length <= 500) || 'Message must be less than 500 characters'
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+/.test(v) || 'E-mail must be valid'
    ],
    select: null,
    items: [
      'Problem during navigation',
      'Report abusive content',
      'Fake news',
      'Suggestons'
    ],
    text: ''
  }),

  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.showSnack = true
        this.reset()
      }
    },
    reset() {
      this.$refs.form.reset()
    }
  }
}
</script>
