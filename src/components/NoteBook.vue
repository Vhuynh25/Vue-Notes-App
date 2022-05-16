<template>
  <div class="notebook">
    <ExistingNote 
    v-for="(note) in notes"
    v-bind:text="note.text"
    v-bind:date="note.date"
    v-bind:id="note.id"
    v-bind:key="note.id"
    v-on:delete-note="handleDeleteNote"
    ></ExistingNote>
    <NewNote v-on:new-note="handleNewNote">
    </NewNote>
  </div>
</template>

<script setup>

import {ref} from 'vue'
import ExistingNote from './ExistingNote.vue'
import NewNote from './NewNote.vue'

let noteId = 0

const notes = ref([])

function handleNewNote(noteText){

  var today = new Date().toLocaleTimeString()

  let new_notes = notes.value.map((x)=>x);

  new_notes.push(
    {
        id: noteId++,
        text: noteText,
        date: today
    }
  )
  notes.value = new_notes
}

function handleDeleteNote(noteId){
  let old_notes = notes.value.map((x)=>x);

  let new_notes = old_notes.filter(
    note => note.id != noteId
  )
  notes.value = new_notes
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.notebook
{
  background-color: grey;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
</style>