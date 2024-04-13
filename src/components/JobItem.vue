<template>
  <div class="job">
    <div class="job__header">
      {{ job.title }} <span>${{ job.salary }}</span>
    </div>
    <div class="job__text">{{ job.location }}</div>
    <div class="job__text">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam nostrum iusto, perspiciatis delectus labore id
      sed magnam itaque laborum incidunt. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam nostrum
      iusto, perspiciatis delectus labore id sed magnam itaque laborum incidunt.
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue"

export default defineComponent({
  name: "Job",
  props: {
    job: { type: Object, required: true }
  },

  setup() {}
})
</script>
<style scoped>
.job {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 10px;
  margin-bottom: 10px;
  background: #fff;
  border: 1px solid #979696;
  border-radius: 10px;
  box-shadow: 0 0 2px 0 rgba(0, 0, 0, 10%);
}
.job__header {
  display: flex;
  align-items: center;
  gap: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid #ccc;
  font-weight: 600;
}
.job__header span {
  padding: 2px 4px;
  border-radius: 4px;
  border: 1px solid #237331;
  color: #237331;
  font-size: 12px;
  background: rgba(0, 0, 0, 5%);
}
.job__text {
  font-size: 14px;
  color: #000;
}
</style>
