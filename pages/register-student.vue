<template>
  <div class="container mt-5">
    <h2 class="text-center">Enroll New Student</h2>
    <form class="form-group" inline @submit.prevent="submitForm">
      <label for="surname">Surname: </label>
      <b-form-input
        id="surname"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Jon"
        required
        v-model="surname"
      ></b-form-input>

      <label for="firstname">First Name: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          id="firstname"
          placeholder="Doe"
          required
          v-model="firstname"
        ></b-form-input>
      </b-input-group>

      <label for="othername">Other Name: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          id="othername"
          placeholder="Akpan"
          required
          v-model="othername"
        ></b-form-input>
      </b-input-group>

      <div>
        <label for="class">Class: </label>
        <b-form-select
          v-model="selectClass"
          :options="options"
          id="class"
        ></b-form-select>
      </div>
      <label for="amountPaid">Amount paid: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
        id="amountPaid" 
        type="number" 
        required 
        v-model="amountPaid"
        ></b-form-input>
      </b-input-group>
      <div class="mb-2 mr-sm-2 mb-sm-0">
        <label for="paymentStatus">Payment Status:</label>
        <b-form-select
          v-model="paymentStatus"
          :options="array"
          id="paymentStatus"
        ></b-form-select>
      </div>
      <b-button type="submit" variant="primary" class="mt-3">Submit</b-button>
    </form>
  </div>
</template>

<script>
  import axios from 'axios';
export default {
  data() {
    return {
      firstname: '',
      surname: '',
      othername: '',
      amountPaid: null,
      selectClass: null,
      options: [
        { value: null, text: "Please select a class" },
        { value: "pre nursery", text: "Pre Nursery" },
        { value: "Nursery 1", text: "Nursery 1" },
        { value: "Nursery 2", text: "Nursery 2" },
        { value: "Transition", text: "Transition" },
        { value: "Primary 1", text: "Primary 1" },
        { value: "Primary 2", text: "Primary 2" },
        { value: "Primary 3", text: "Primary 3" },
        { value: "Primary 4", text: "Primary 4" },
        { value: "Primary 5", text: "Primary 5" },
      ],

      paymentStatus: null,
      array: [
        { value: null, text: "Select payment status" },
        { value: "cleared", text: "Cleared" },
        { value: "not cleared", text: "Part payment" },
      ],
    };
  },
  methods: {
    submitForm(){
      fetch('https://student-dashboard-8b46f-default-rtdb.firebaseio.com/students.json',{
        method: "POST",
        headers: {
          'Content-type': 'application/json'
        },
        body: JSON.stringify({
          firstname: this.firstname,
          surname: this.surname,
          othername: this.othername,
          amount: this.amountPaid,
          class: this.selectClass,
          status: this.paymentStatus
        })
      });

      this.firstname= '',
      this.surname= '',
      this.othername= '',
      this.amountPaid= null,
      this.selectClass = null,
      this.paymentStatus= null

    },
  },
};
</script>
