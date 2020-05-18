<template>
    <section>
        <ul>
            <li v-for="(todoItem, index) in propsdata" class="shadow"> <!--index는 v-for 디렉티브에서 기본적으로 제공하는 변수-->
                <i class="checkBtn fas fa-check" aria-hidden="true"></i>
                {{ todoItemv}}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
                    <i class="far fa-trash-alt" aria-hidden="true"></i>
                </span>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props: ['propsdata'],
    methods:{
        removeTodo(todoItem, index){
            this.$emit('removeTodo', todoItem, index);
            t//his.todoItems.splice(index, 1); // splice() > 배열의 특정 인덱스에서 부여한 숫자만큼 인덱스 삭제
        }
    }
}
</script>

<style scoped>
    ul{list-style-type: none; padding-left: 0px; margin-top: 0; text-align: left;}
    li{display: flex; min-height: 50px; height: 50px; line-height: 50px; margin: 0.5rem 0; padding: 0 0.9rem; background:#fff; border-radius: 5px;}
    .checkBtn{line-height: 45px; color:#62acde; margin-right: 5px;}
    .removeBtn{margin-left: auto; color:#de4343;}
</style>