<script setup>
import courses from '../courses';
import {useRoute} from 'vue-router';
import LessonSummary from "../components/LessonSummary.vue";
const route = useRoute();
const courseId = route.params.courseId;
const course = courses.find(course => course.id === parseInt(courseId));
const {title, lessons} = course;
</script>

<template>
    <div>
        <header>
            <p>
                <router-link :to="{name: 'home'}">Back to courses</router-link>
            </p>
            <h1>{{title}}</h1>
            <p>{{description}}</p>
            <router-link :to="`/courses/${courseId}/lessons/${course.lessons[0].id}`">Start Course</router-link>
        </header>
        <div>
            <LessonSummary v-for="(lesson, index) in lessons" :key="index" :course-id="courseId" :lesson="lesson" :num="index + 1" />
        </div>
    </div>
</template>