<script setup>

define props ([
    'studenName',
    'studentId',
    'email',
    'course',
    'rating',
    'recommendation',
    'feedback'
])

<script>

<template>
  <div>
    <h2>Feedback Display</h2>
    <p>Student Name: {{ studenName }}</p>
    <p>Student ID: {{ studentId }}</p>
    <p>Email: {{ email }}</p>
    <p>Course: {{ course }}</p>
    <p>Rating: {{ rating }}</p>
    <p>Recommendation: {{ recommendation }}</p>
    <p>Feedback: {{ feedback }}</p>
  </div>
</template> 