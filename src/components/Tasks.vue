<template>
    <div :key="task.id" v-for="task in tasks">
        <Task
            @toggle-reminder="$emit('toggle-reminder', $event)"
            @delete-task="$emit('delete-task', $event)"
            :task="task"
        />
    </div>
</template>
<script>
import Task from './Task.vue';

export default {
    name: 'Tasks',
    props: {
        tasks: {
            type: Array,
            default: [],
        },
    },
    components: {
        Task,
    },
    emits: ['delete-task', 'toggle-reminder'],
};
</script>
