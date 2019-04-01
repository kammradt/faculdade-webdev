<template>
  <VApp>
    <VContent>
      <SuperiorToolbar />
      <NewsContent />
      <MyFooter />
    </VContent>
  </VApp>
</template>

<script>
import SuperiorToolbar from '@/components/SuperiorToolbar'
import NewsContent from '@/components/NewsContent'
import MyFooter from '@/components/MyFooter'

export default {
  name: 'Index',
  components: { SuperiorToolbar, MyFooter, NewsContent }
}
</script>
