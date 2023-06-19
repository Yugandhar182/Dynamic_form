<script>
  import { onMount } from 'svelte';

  let formFields = [];
  let formId = "72fbc0da-3810-4ad9-a922-1845f8974eb7"; // Set the default form ID

  async function generateDynamicForm() {
    const apiKey = "TEST45684CB2A93F41FC40869DC739BD4D126D77";

    const response = await fetch(`https://api.recruitly.io/api/candidateform/details/${formId}?apiKey=${apiKey}`);
    const data = await response.json();

    formFields = data.fields;
  }

  function handleSubmit(event) {
    event.preventDefault();
    // Handle form submission
    // You can access the form data using event.target
  }

  onMount(() => {
    generateDynamicForm();
  });
</script>

<main>
  <form on:submit="{handleSubmit}">
    {#each formFields as field}
      {#if field.id === 'fullName'}
        <div class="form-group">
          <label for="{field.id}">{field.label}</label>
          <input type="text" class="form-control" id="{field.id}" bind:value="{field.value}" placeholder="{field.placeholder}">
        </div>
      {:else if field.type === 'email'}
        <div class="form-group">
          <label for="{field.id}">{field.label}</label>
          <input type="email" class="form-control" id="{field.id}" bind:value="{field.value}" placeholder="{field.placeholder}">
        </div>
      {:else if field.type === 'textarea'}
        <div class="form-group">
          <label for="{field.id}">{field.label}</label>
          <textarea class="form-control" id="{field.id}" bind:value="{field.value}" placeholder="{field.placeholder}" rows="3"></textarea>
        </div>
      {:else}
        <div class="form-group">
          <label for="{field.id}">{field.label}</label>
          <input type="text" class="form-control" id="{field.id}" bind:value="{field.value}" placeholder="{field.placeholder}">
        </div>
      {/if}
    {/each}

    <button type="submit" class="btn btn-primary">Submit</button>
  </form>
</main>

<style>
  .form-group {
    margin-bottom: 20px;
  }
</style>
