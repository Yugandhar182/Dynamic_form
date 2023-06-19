<script>
  import { onMount } from 'svelte';
  import 'bootstrap/dist/css/bootstrap.min.css'

  let formFields = [];
  let formId = '72fbc0da-3810-4ad9-a922-1845f8974eb7';
  let fullname = '';
  let email = '';
  let mobile = '';

  function addFormField() {
    formFields = [...formFields, { label: '', value: '' }];
  }

  function fetchData() {
    fetch(`https://api.recruitly.io/api/candidateform/details/${formId}?apiKey=TEST45684CB2A93F41FC40869DC739BD4D126D77`)
      .then(response => response.json())
      .then(data => {
        console.log('API Response:', data);
        fullname = data.fullname;
        email = data.email;
        mobile = data.mobile;
        // Update the form fields based on the fetched data
        formFields = Object.entries(data).map(([label, value]) => ({ label, value }));
      })
      .catch(error => {
        console.error('API Error:', error);
      });
  }

  function handleSubmit() {
    // Perform any necessary actions on form submission
    // You can access the form data using the component's reactive variables, such as fullname, email, mobile, and formFields
    console.log('Form Submitted');
    console.log('Fullname:', fullname);
    console.log('Email:', email);
    console.log('Mobile:', mobile);
    console.log('Form Fields:', formFields);
  }

  onMount(() => {
    // Add an event listener to form fields
    function handleFieldChange(event) {
      formId = event.target.value;
    }

    const fields = document.querySelectorAll('input[type="text"]');
    fields.forEach(field => field.addEventListener('input', handleFieldChange));
  });
</script>

<style>
  .form-container {
    max-width: 400px;
    margin: 0 auto;
  }

  .form-container label {
    margin-bottom: 0.5rem;
  }

  .form-container button {
    margin-top: 1rem;
  }
</style>

<div class="form-container">
  <form on:submit|preventDefault={handleSubmit}>
    <div class="mb-3">
      <label for="fullname" class="form-label">Fullname</label>
      <input type="text" id="fullname" class="form-control" bind:value={fullname} />
    </div>

    <div class="mb-3">
      <label for="email" class="form-label">Email</label>
      <input type="text" id="email" class="form-control" bind:value={email} />
    </div>

    <div class="mb-3">
      <label for="mobile" class="form-label">Mobile</label>
      <input type="text" id="mobile" class="form-control" bind:value={mobile} />
    </div>

    {#each formFields as field, i}
      <div class="mb-3">
        <label for="field{i}" class="form-label">{field.label}</label>
        <input type="text" id="field{i}" class="form-control" bind:value={field.value} />
      </div>
    {/each}

    <button type="button" class="btn btn-primary" on:click={addFormField}>Add Field</button>
    <button type="button" class="btn btn-primary" on:click={fetchData}>Fetch Data</button>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>
</div>
