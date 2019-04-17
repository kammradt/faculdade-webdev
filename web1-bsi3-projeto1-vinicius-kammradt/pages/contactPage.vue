<template>
  <VApp>
    <VContent>
      <SuperiorToolbar />
      <ContactForm />
      <MyFooter />
    </VContent>
  </VApp>
</template>

<script>
import SuperiorToolbar from '@/components/SuperiorToolbar'
import ContactForm from '@/components/ContactForm'
import MyFooter from '@/components/MyFooter'

export default {
  components: {
    SuperiorToolbar,
    ContactForm,
    MyFooter
  }
}
</script>
