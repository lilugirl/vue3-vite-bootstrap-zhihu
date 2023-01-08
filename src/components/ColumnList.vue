<template>
  <div class="row">
    <div v-for="column in columnList" :key="column.id" class="col-4 mb-4">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
            <img :src="column.avatar" :alt="column.title" class="rounded-circle border border-light w-25 my-3" />
            <h5 class="card-title">{{ column.title }}</h5>
            <p class="card-text text-left">{{ column.description }}</p>
            <a class="btn btn-outline-primary" href="#">进入专栏</a>
        </div>

      </div>
    </div>
  </div>
</template>
<script lang="ts">

import { PropType, computed } from 'vue'
import avatar from  '../assets/column.jpeg'
export interface ColumnProps{
  id:number;
  title:string;
  avatar?:string;
  description:string;
}

export default {
  props:{
    list:{
      type:Array as PropType<ColumnProps[]>,
      required:true
    }
  },
  setup(props){
    const columnList = computed(() => {
      return props.list.map(column => {
        if (!column.avatar) {
          column.avatar=avatar
        }
        return column
      })
    })

    return {
      columnList
    }
  }
}
</script>