<script>
  import { onMount } from 'svelte';
  import 'bootstrap/dist/css/bootstrap.min.css';

  let fields = [];
  
  let currentURL = '';
  let stringAfterLastSlash = '';
  let receiveUpdatesByEmail = false;
  let receiveUpdatesBySMS = false;
  let acceptPrivacyPolicy = false;


  function extractStringAfterLastSlash(url) {
    const lastIndex = url.lastIndexOf('/');
    return url.substring(lastIndex + 1);
  }

  onMount(() => {
    currentURL = window.location.href;
    stringAfterLastSlash = extractStringAfterLastSlash(currentURL);
  });

  onMount(async () => {
    try {
      const response = await fetch(`https://api.recruitly.io/api/candidateform/details/${stringAfterLastSlash}?apiKey=TEST45684CB2A93F41FC40869DC739BD4D126D77`);
      if (!response.ok) {
        throw new Error(`Request failed with status ${response.status}`);
      }
      const data = await response.json();
      console.log('Data:', data);
      if (Array.isArray(data.fields)) {
        fields = data.fields;
      } else {
        throw new Error('Response data does not contain the "fields" property');
      }
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  });
</script>

<style>
  .form-group {
    margin-bottom: 1rem;
  }
</style>

{#if fields.length > 0}
  <h2>Form Fields:</h2>
  <form>
    {#each fields as field (field.code)}
  
  {#if field.code === 'EMAIL'}
    <div class="form-group">
      <label for="email">{field.label}</label>
      <input class="form-control" type="email"  name={field.code} placeholder="Write your Email">
    </div>
  {/if}
  {#if field.code === 'CV'}
  <div class="form-group">
    <h4>{field.label}</h4>
    <input class="form-control-file w-100" type="file"  name={field.code} accept=".pdf,.doc,.docx" >
  </div>
{/if}
  {#if field.code === 'MOBILE'}
    <div class="form-group">
      <label for="mobile">{field.label}</label>
      <input class="form-control" type="tel" name={field.code} placeholder="Enter Your Mobile Number">
    </div>
  {/if}
  {#if field.code === 'ADDRESS'}
    <div class="form-group">
      <label for="addressLine">{field.label}</label>
      <input class="form-control" type="text"  name={field.code} placeholder="Write Your full Address">
    </div>
  {/if}
  {#if field.code === 'FULL_NAME'}
    <div class="form-group">
      <label for=" Enter FullName" >{field.label}</label>
      <input class="form-control" type="text"  name={field.code} placeholder="Enter Your FullName">
    </div>
  {/if}
  {#if field.code === 'LANGUAGES'}
  <div class="form-group">
    <label for="Languages">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="languages">
  </div>
  {/if}
  {#if field.code==='weav04e7bf4b25574e419d7a36399d579c86'}
  <div class="form-group">
    <label for="Experince">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Experince">
  </div>
  {/if}
  {#if field.code==='weava647dfe7b2c44d7cbf1be28e231018d1'}
  <div class="form-group">
    <label for="Date of birth">{field.label}</label>
    <input class="form-control" type="Date"  name={field.code} placeholder="Date of Birth">
  </div>
  {/if}
  {#if field.name==='Years of experience'}
  <div class="form-group">
    <label for="Years of experience">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Years of Experience">
  </div>
  {/if}
  {#if field.code==='QUALIFICATION'}
  <div class="form-group">
    <label for="Qualification">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Qualification">
  </div>
  {/if}
  {#if field.code==='RATING'}
  <div class="form-group">
    <label for="Rating">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Rating">
  </div>
  {/if}
  {#if field.code==='GENDER'}
  <div class="form-group">
    <label for="gender">{field.label}</label>
    <input class="form-control" type="text"  id="gender" name={field.code} placeholder="Gender" >
    </div>
  {/if}
  {#if field.code==='INDUSTRY'}
  <div class="form-group">
    <label for="industry">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Industry" >
    </div>
  {/if}
  {#if field.code === 'LANGUAGES_LEVEL'}
  <div class="form-group">
    <label for="Languages Level">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Languages Level">
  </div>
  {/if}
  {#if field.code==='PROFESSIONAL_QUALIFICATION'}
  <div class="form-group">
    <label for="Professional qualification">{field.label}</label>
    <input class="form-control" type="text"  name={field.code} placeholder="Professional qualification">
  </div>
  {/if}
  
  
{/each}
    <div class="form-group">
      <label>
        <input type="checkbox" bind:checked={receiveUpdatesByEmail}> I am happy to receive updates by Email.
      </label>
    </div>
    <div class="form-group">
      <label>
        <input type="checkbox" bind:checked={receiveUpdatesBySMS}> I am happy to receive updates by SMS.
      </label>
    </div>
    <div class="form-group">
      <label>
        <input type="checkbox" bind:checked={acceptPrivacyPolicy}> Click here to indicate that you have read and accept the privacy policy of HireOptica.
      </label>
    </div>
    <button class="btn btn-primary" type="submit">Submit</button>
  </form>
{/if}

