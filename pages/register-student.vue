<template>
  <div class="container mt-5">
    <h2 class="text-center">Enroll New Student</h2>
    <b-form-group inline>
      <label for="surname">Surname: </label>
      <b-form-input
        id="surname"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Jon"
        required
      ></b-form-input>

      <label for="firstname">First Name: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input id="firstname" placeholder="Doe" required></b-form-input>
      </b-input-group>

      <label for="othername">Other Name: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          id="othername"
          placeholder="Akpan"
          required
        ></b-form-input>
      </b-input-group>

      <label for="othername">Other Name: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          id="othername"
          placeholder="Akpan"
          required
        ></b-form-input>
      </b-input-group>
      <div>
        <label for="class">Class: </label>
      <b-form-select v-model="selected" :options="options" id="class"></b-form-select>
      </div>
    </b-form-group>
    <label for="amountPaid">Amount paid: </label>
      <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
        <b-form-input
          id="amountPaid"
          type="number"
          required
        ></b-form-input>
      </b-input-group>
      <b-button type="submit" variant="primary" class="mt-3">Submit</b-button>
   
      
  </div>
</template>


<script>
export default {
  data() {
      return {
        selected: null,
        options: [
          { value: null, text: 'Please select a class' },
          { value: 'a', text: 'Pre Nursery' },
          { value: 'b', text: 'Nursery 1' },
          { value: { C: '3PO' }, text: 'Nursery 2' },
          { value: 'd', text: 'Transition' },
          { value: 'd', text: 'Primary 1' },
          { value: 'd', text: 'Primary 2' },
          { value: 'd', text: 'Primary 3' },
          { value: 'd', text: 'Primary 4' },
          { value: 'd', text: 'Primary 5' },
          
        ]
      }
    }
};
</script>