<template>
    <p :class="['todo-item', todoProps.completed && 'is-completed']"  >
        <input type="checkbox"  
        :checked="todoProps.completed"
        @change="markComplete" >
        {{todoProps.title}}
        <button 
        class="deleteBtn"
        @click="deleteTodo"
        >Delete</button>
    </p>
</template>

<script>



export default {
    name: 'TodoItem',
    props: ['todoProps'],
    setup(props, context) {
        const markComplete = () => {
            context.emit('item-completed', props.todoProps.id);
        }
        const deleteTodo = () => {
            context.emit('delete-btn', props.todoProps.id);
        }
        return {
            markComplete,
            deleteTodo
        }
    }
}
</script>

<style>
.todo-item {
    background: #f4f4f4;
    padding: 10px;
    position: relative;
}
.is-completed {
    text-decoration: line-through;
}
.deleteBtn {
    background: #ff0000;
    color: #fff;
    border: 0;
    height: 32px;
    width: 72px;
    border-radius: 4px;
    font-weight: 600;
    cursor: pointer;
    padding: 4px 0px;
    position: absolute;
    top: 4px;
    right: 0;
}
</style>