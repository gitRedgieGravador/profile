<template>
  <q-page>
      <div class="q-pa-xs">
        <div class="row justify-center q-gutter-sm">
          <q-intersection
            v-for="index in 60"
            :key="index"
            transition="scale"
            class="example-item">
            <q-card flat class="q-ma-sm">
              <img src="https://cdn.quasar.dev/img/mountains.jpg">
              <q-card-section>
                <div class="text-h6">Card #{{ index }}</div>
                <div class="text-subtitle2">by John Doe</div>
              </q-card-section>
            </q-card>
          </q-intersection>
        </div>
    </div>
  </q-page>
</template>
<script>
export default {
  name: 'PageIndex'
}
</script>
<style scoped>
.example-item{
  height: 290px;
  width: 290px;
}
</style>