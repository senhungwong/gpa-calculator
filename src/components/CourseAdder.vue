<template>
    <div style="margin-bottom: 15px">
        <form>
            <input type="text" v-model="grade" placeholder="Grade">
            <input type="number" v-model="credit" placeholder="Credit">
            <button @click="addCourse()">Add Course</button>
            <button @click="clear()">Clear</button>
        </form>
    </div>
</template>

<script>
import store from '../store';

export default {
    data() {
        return {
            grade: null,
            credit: null
        }
    },
    methods: {
        addCourse() {
            store.commit('addCourse', {grade: this.grade, credit: this.credit});
            this.grade = null;
            this.credit = null;
        },
        clear() {
            store.commit('clearCourses');
        }
    }
}
</script>

<style>

</style>
