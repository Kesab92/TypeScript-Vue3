<template>
    <div class="job-list">
        <p>Ordered by {{ order }}</p>
        <ul>
            <li v-for="job in jobs" :key="job.id">
                <h2>{{ job.title }} in {{ job.location }} </h2>
                <div class="salary">
                    <p>{{ job.salary }} rupees</p>
                    <div class="description">
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                            Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                             when an unknown printer took a galley of type and scrambled it to make a type specimen book.
                             It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.
                              It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages,
                            and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum. 
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '../../types/Job'
import OrderTerm from '../../types/OrderTerm'

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>,
        },
        order: {
            required:true,
            type: String as PropType<OrderTerm>
        }
    }

})
</script>

<style scoped>
 .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
    flex-direction: column;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>