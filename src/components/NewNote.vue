<template>
  <div class="new_note">
    <textarea class="text" id="text" ref="noteText"></textarea>
      
    <div class="foot">
        <small class=date></small>
        <button class="save" @click="saveButtonClicked">
          save
        </button> 
    </div>
  </div>
</template>

<script setup>
import {ref, defineEmits} from 'vue'

const noteText = ref(null);
const emit = defineEmits(['new-note'])

//var notes = []
//const state = reactive(notes)
//onMounted(() => 
  //{
  //  noteText.
  //}
//)

function saveButtonClicked()
{
  emit('new-note', noteText.value.value)
}

// isEditable = false

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.new_note
{
  background-color: cyan;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-width: 200px;
  min-height: 150px;
  border: 1px solid;
  align-self: end;
  padding: 0;
  margin: 10px;
}

.foot
{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.save
{
  border: 1px solid;
  margin: 3px;
}

.text
{
  background: transparent;
  border: 0;
  
  resize: none;
}
</style>