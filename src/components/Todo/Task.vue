<template>
    <div>
        <v-list-item 
        @click="$store.commit('doneTask',task.id)"
        :class="{'teal lighten-4': task.done}"
        :ripple="false"
        class="white"
        >
            <template v-slot:default>
            <v-list-item-action>
                <v-checkbox
                :input-value="task.done"
                color="primary"
                ></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
                <v-list-item-title :class="{'text-decoration-line-through': task.done }">{{ task.title }}</v-list-item-title>
            </v-list-item-content>

            <v-list-item-action v-if="task.dueDate">
                <v-list-item-action-text>
                  <v-icon small>mdi-calendar</v-icon>
                  {{ task.dueDate | formattedDate}}
                </v-list-item-action-text>
                
              </v-list-item-action>

            <v-list-item-action>
                <task-menu :task='task'/>
            </v-list-item-action>

            <v-list-item-action
            v-if="$store.state.sorting"
            >
                <v-btn
                    color="primary"
                    class="handle"
                    icon
                >
                    <v-icon>mdi-drag-variant</v-icon>
                </v-btn>
            </v-list-item-action>
            </template>
        </v-list-item>
        <v-divider></v-divider>
    </div>
</template>

<script>
import { format } from 'date-fns'
export default {
    props: ['task'],
    filters: {
      formattedDate(value) {
          return format(new Date(value), 'MMM d')
      }
    },
    components: {
        'task-menu': require('@/components/Todo/TaskMenu.vue').default
    }
}
</script>
<style lang="sass">
  .sortable-ghost
    opacity: 0
</style>
