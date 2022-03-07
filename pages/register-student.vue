<template>
  <div class="container mt-5">
    <h2 class="text-center">Enroll New Student</h2>
    <b-form-group inline @submit.prevent="submitForm">
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
    </b-form-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstname: '',
      surname: '',
      othername: '',
      amountPaid: 0,
      selectClass: null,
      options: [
        { value: null, text: "Please select a class" },
        { value: "a", text: "Pre Nursery" },
        { value: "b", text: "Nursery 1" },
        { value: "c", text: "Nursery 2" },
        { value: "d", text: "Transition" },
        { value: "e", text: "Primary 1" },
        { value: "f", text: "Primary 2" },
        { value: "g", text: "Primary 3" },
        { value: "h", text: "Primary 4" },
        { value: "i", text: "Primary 5" },
      ],

      paymentStatus: null,
      array: [
        { value: null, text: "Select payment status" },
        { value: "a", text: "Cleared" },
        { value: "b", text: "Part payment" },
      ],
    };
  },
  method: {
    submitForm(){
      axios.post('https://el-gibbor-dashboard-default-rtdb.europe-west1.firebasedatabase.app/student.json',{
        hearder: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          firstname: this.firstname,
          surname: this.surname,
          othername: this.othername,
          amount: this.amountPaid,
          class: this.selectedClass,
          status: this.paymentStatus
        })
      });

       this.firstname= '',
      this.surname= '',
      this.othername= '',
      this.amountPaid= 0,
      this.selectClass = null,
      this.paymentStatus= null

    },
  },
};
</script>
