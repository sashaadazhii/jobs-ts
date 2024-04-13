<template>
  <div class="app">
    <JobList :jobs="jobs" />
    <!-- <div>name: {{ name }}</div>
    <div>age: {{ age }}</div>
    <button @click="changeName('new link here')">Change name</button>
    <button @click="changeAge(45)">Change age</button> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue"
import type Job from "./types/Job"
// import type SortOrder from "./types/SortOrder"
import JobList from "./components/JobList.vue"
export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { id: "1", title: "First job", location: "City 1", salary: 10100 },
      { id: "2", title: "Second job", location: "City 2", salary: 50000 },
      { id: "3", title: "Third job", location: "City 3", salary: 3500 },
      { id: "4", title: "Fourth job", location: "City 4", salary: 20000 },
      { id: "5", title: "Fifth job", location: "City 5", salary: 34500 },
      { id: "6", title: "Sixth job", location: "City 6", salary: 4500 }
    ])
    // const order = ref<SortOrder>("title")
    // const sort = (userOrder: SortOrder) => {
    //   order.value = userOrder
    // }
    return { jobs }
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as string | number
    // })
    // state.name = "ererer"
    // // state.name = 000 //error
    // return { ...toRefs(state) }
    //--------------------------
    // const name = ref("Link")
    // const age = ref<string | number>(25)
    // age.value = 40
    // return { name, age }
  },
  data() {
    return {
      // name: "Link",
      // age: 25 as string | number
    }
  },
  methods: {
    // changeName(name: string) {
    //   this.name = name
    // },
    // changeAge(age: number | string) {
    //   this.age = age
    // }
  }
})
</script>

<style scoped></style>
