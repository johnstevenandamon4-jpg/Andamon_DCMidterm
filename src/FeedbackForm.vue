<script setup>
import { reactive } from 'vue'

const props = defineProps({
  defaultCourse: String,
  defaultYear: String
})

const emit = defineEmits(['register-submitted'])

const form = reactive({
  studname: '',
  studentId: '',
  email: '',
  course: '',
  rating: '',
  recommendation: '',
  feedback: ''
})

</script>

<template>
  <div>
    <h2>Feedback Form</h2>
    <p>Course: {{ defaultCourse }}, Year: {{ defaultYear }}</p>

    <form @submit.prevent="submitFeedback">
      <div>
        <div>
          <label>Student Name:</label>
          <input type="text" v-model="form.studname" required />
        </div>
        <div>
          <label>Student ID:</label>
          <input type="text" v-model="form.studentId" required />
        </div>
      </div>
      <div>
        <label>Email:</label>
        <input type="email" v-model="form.email" required />
      </div>

      <div>
        <label>Course:</label>
        <input type="text" v-model="form.course" required />
        <div>
            <label><input type="dropdown" v-model="form.course" :value="defaultCourse" />BSIT</label>
            <label><input type="dropdown" v-model="form.course" :value="defaultCourse" />BSCS</label>
            <label><input type="dropdown" v-model="form.course" :value="defaultCourse" />BSIS</label>
      </div>

        <div>
        <label>Rating:</label>
        <div>
          <label><input type="radio" v-model="form.rating" value="1" required /> 1</label>
          <label><input type="radio" v-model="form.rating" value="2" required /> 2</label>
          <label><input type="radio" v-model="form.rating" value="3" required /> 3</label>
          <label><input type="radio" v-model="form.rating" value="4" required /> 4</label>
          <label><input type="radio" v-model="form.rating" value="5" required /> 5</label>
        </div>
      </div>

        <div>
            <label>Recommendation:</label>
            <div>
            <label><input type="radio" v-model="form.recommendation" value="Yes" required /> I recommend this course to other students</label>
            <label><input type="radio" v-model="form.recommendation" value="No" required /> I do not recommend this course</label>
            </div>
       <div>
        <label>
          <input type="checkbox" v-model="form.agreeTerms" required /> I agree to the terms and conditions
        </label>
      </div>
      <div>
        <label>Feedback:</label>
        <textarea v-model="form.feedback" placeholder="Tell something about the course" rows="3" required></textarea>
      </div>
    </form>
  </div>
</template>

