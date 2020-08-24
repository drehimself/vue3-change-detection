<template>
  <h2>Object Change Detection</h2>
  <div>
    <button @click="addFieldToObject">Add field to Object</button>
    <button @click="deleteFieldFromObject">Delete field from Object</button>
  </div>
  <div class="mt">
    {{ personObject }}
  </div>

  <h2>Array Change Detection</h2>
  <div>
    <button @click="changeArrayUsingIndex">Change Array using index</button>
    <button @click="changeArrayLength">Change Array length</button>
    <button @click="pushToArray">Push to Array</button>
  </div>
  <div class="mt">
    {{ peopleArray }}
  </div>

</template>

<script>
import { ref, reactive } from 'vue'
export default {
  setup() {
    const personObject = reactive({
      name: 'Andre',
    })

    function addFieldToObject() {
      personObject.age = 36
    }

    function deleteFieldFromObject() {
      delete personObject.age
    }

    const peopleArray = ref([
      'Andre', 'Bob', 'Sally',
    ])

    function changeArrayUsingIndex() {
      peopleArray.value[0] = 'Aaron'
    }

    function changeArrayLength() {
      peopleArray.value.length = 1
    }

    function pushToArray() {
      peopleArray.value.push('William')
    }

    return {
      personObject,
      addFieldToObject,
      deleteFieldFromObject,
      peopleArray,
      changeArrayUsingIndex,
      changeArrayLength,
      pushToArray
    }
  }
}
</script>

<style scoped>
.mt {
  margin-top: 8px;
}
</style>
