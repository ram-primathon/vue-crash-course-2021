<template>
    <header>
        <h1>{{ title }}</h1>
        <Button
            @btn-click="$emit('toggle-form-visibility')"
            :text="showAddTask ? 'Close' : 'Add Task'"
            :color="showAddTask ? 'red' : 'green'"
        />
    </header>
</template>

<script>
import Button from './Button.vue';

//! Way 1 ..................
// export default {
//     name: 'Header',
//     props: ['title'],
// };

//! Way 2 ..................
// export default {
//     name: 'Header',
//     props: {
//         title: String,
//     },
// };

//! Way 3 .....................
export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: 'Task Tracker',
        },
        showAddTask: Boolean,
    },
    components: {
        Button,
    },
};
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px;
    margin-bottom: 20px;
}
</style>
