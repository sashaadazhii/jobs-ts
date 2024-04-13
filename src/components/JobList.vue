<template>
  <div class="btns">
    <button @click="sort('salary')">Order by salary</button>
    <button @click="sort('title')">Order by title</button>
    <button @click="sort('location')">Order by location</button>
  </div>
  <div>Ordered by {{ order }}</div>
  <transition-group name="list" tag="div">
    <JobItem v-for="job in sortedJobs" :key="job.id" :job="job" />
  </transition-group>
</template>
<script lang="ts">
import { defineComponent, ref, computed } from "vue"
import type { PropType } from "vue"
import type Job from "../types/Job"
import JobItem from "@/components/JobItem.vue"
import type SortOrder from "../types/SortOrder"

export default defineComponent({
  name: "JobList",
  components: { JobItem },
  props: { jobs: { type: Array as PropType<Job[]>, required: true } },

  setup(props) {
    const order = ref<SortOrder>("title")
    const sort = (userOrder: SortOrder) => {
      order.value = userOrder
    }

    const sortedJobs = computed(() => {
      //[...props.jobs] - because it's a prop
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[order.value] > b[order.value] ? 1 : -1
        // return a[props.order] > b[props.order] ? 1 : -1
      })
    })
    return { sort, order, sortedJobs }
  }
})
</script>

<style scoped>
.btns {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
}
button {
  padding: 8px 12px;
  border-radius: 6px;
  border: 1px solid #3d799c;
  color: #3d799c;
  font-weight: 600;
  cursor: pointer;
}
.list-move {
  transition: all 0.5s;
}
</style>
