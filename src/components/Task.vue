<template>
    <!-- class 바인딩하기 : task.reminder가 true인 경우 삼항연산자를 사용하여 처리, 중요! task라는 class가 기본 베이스로 있는 경우 []의 두번째 인자로 넣어준다. -->
    <div :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }}
            <i
                @click="onDelete(task.id)"
                class="fas fa-times"
            ></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Task',
        props: {
            task: Object,
        },
        methods: {
            onDelete(id) {
                this.$emit('delete-task', id)
            }
        }
    }
</script>

<style scope>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>