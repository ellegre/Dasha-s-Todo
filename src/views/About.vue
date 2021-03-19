<template>
  <div class="about pa-6">
    <h1 class="about-title text-md-h5 mb-5">About {{ $store.state.appTitle}}</h1>
    <p>This app was created for a nice girl named Dasha, but hope that it will be useful for you too!</p>
    <p class="mb-3">You can add tasks, change a task name, set a due date, filter the tasks, mark the tasks as complete and delete them.</p>
    <p><span class="bg-text bold-text">Create a new task.</span>Tap Add a mew task, enter a task, press + or Enter on a keyboard.</p>
    <p><span class="bg-text bold-text">Change a task.</span>Tap the three dots icon in the task you want to edit. Change the task info.</p>
    <p><span class="bg-text bold-text">Mark a task as complete.</span>To the left of a task, tap a checkbox<v-icon>mdi-checkbox-blank-outline</v-icon>.</p>
    <p><span class="bg-text bold-text">Delete a task.</span>Tap the three dots icon you want to edit. Delete the task.</p>
    <p><span class="bg-text bold-text">Reorder Tasks.</span> This one is really simple. The app let you easily re-organize 
    the order of the todos on your list. Just pick up on the <span class="bold-text">Sorting</span> option from task menu and drag it using sorting icon
    <v-icon>mdi-drag-variant</v-icon>.
    Press <span class="bold-text">Done sorting</span> button when finished.</p>
  </div>
</template>

<style lang="sass">
  .about-title 
    font-size: 24px
  .bold-text
    font-weight: 700
  .bg-text 
    font-size: 18px    
</style>
