<template>
  <li class="note">
    <textarea class="text" id="text" v-bind:value="text"></textarea>
    <div class="foot">
        <small class=date>{{date}}</small>
        <button class="delete" @click="deleteButtonClicked(id)">
          Delete
        </button> 
    </div>
  </li>
</template>

<script setup>
import {defineProps, defineEmits} from "vue"

defineProps(["text", "date", "id"])
const emit = defineEmits(["delete-note"])



function deleteButtonClicked(id)
{
  emit('delete-note', id)
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.note
{
  background-color: rgb(211, 211, 86);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  
  min-width: 200px;
  min-height: 150px;
  margin: 10px;
  border: 1px solid;
}

.foot
{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.text
{
  background: transparent;
  border: 0;
  
  resize: none;
}

.delete
{
  border: 1px solid;
  margin: 3px;
}
</style>