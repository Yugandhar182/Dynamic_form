<script>
  import 'bootstrap/dist/css/bootstrap.min.css'

  let fullName = '';
  let email = '';
  let mobile = '';
  let CandidateCv='';
  let address = '';
  let languages = '';
  let experience = '';
  let qualification = '';
  let yearsOfExperience = '';
  let industry = '';
  let Function = '';
  let dbsCheck = '';
  let fullNRICFINPassportNumber = '';
  let dateOfBirth = '';
  let sectors = '';
  let industries = '';
  let headline = '';
  let gender = '';
  let otherScheduledCaste = '';
  let GENDER = '';

  function handleSubmit() {
    
  }
</script>

<main>
  
   <form on:submit="{handleSubmit}">
          <div class="form-group">
            <label class="blue-label" for="fullName">Full Name</label>
            <input type="text" class="form-control" id="fullName" bind:value="{fullName}"placeholder="Enter Full Name">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="email">Email</label>
            <input type="email" class="form-control" id="email" bind:value="{email}" placeholder="Enter Your email">
          </div>
          <div class="form-group">
            <label class="blue-label" for="mobile">Mobile</label>
            <input type="text" class="form-control" id="mobile" bind:value="{mobile}" placeholder="Enter your Mobile number">
            <select id="mobile" class="form-control" bind:value={mobile}>
              <option value="" disabled>Select a mobile number</option>
              <option value="+1">+1 (USA)</option>
              <option value="+91">+91 (India)</option>
              <option value="+44">+44 (UK)</option>
              <option value="+353">+353 (Ireland)</option>
          </div>
          <div class="form-group">
            <label  class="blue-label" for="candidateCv">Candidate CV</label>
            <input type="file" class="form-control" id="candidateCv" bind:value="{CandidateCv}" >
          </div>
          <div class="form-group">
            <label class="blue-label" for="address">Address/Location</label>
            <textarea class="form-control" id="address" rows="3" bind:value="{address}" placeholder="Address/Location"></textarea>
          </div>
          <div class="form-group">
            <label class="blue-label" for="languages">Languages</label>
            <input type="text" class="form-control" id="languages" bind:value="{languages}" placeholder="Languages">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="experience">Experience</label>
            <input type="text" class="form-control" id="experience" bind:value="{experience}">
          </div>
          <div class="form-group">
            <label class="blue-label" for="qualification">Qualification</label>
            <input type="text" class="form-control" id="qualification" bind:value="{qualification}" placeholder="Qualification">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="yearsOfExperience">Years of Experience</label>
            <input type="text" class="form-control" id="yearsOfExperience" bind:value="{yearsOfExperience}" placeholder="Years of Experince">
          </div>
          <div class="form-group">
            <label class="blue-label" for="industry">Industry</label>
            <input type="text" class="form-control" id="industry" bind:value="{industry}" placeholder="Industry">
          </div>
          <div class="form-group">
            <label class="blue-label" for="jobFunction">Function</label>
            <input type="text" class="form-control" id="jobFunction" bind:value="{Function}" placeholder="Function">
          </div>
          <div class="form-group">
            <label class="blue-label" for="dbsCheck">DBS Check</label>
            <input type="text" class="form-control" id="dbsCheck" bind:value="{dbsCheck}" placeholder="DBS Check">
          </div>
          <div class="form-group">
            <label class="blue-label" for="fullNRICFINPassportNumber">Full NRIC/FIN/Passport Number</label>
            <input type="text" class="form-control" id="fullNRICFINPassportNumber" bind:value="{fullNRICFINPassportNumber}" placeholder="Full NRIC/FIN/Passport Number">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="dateOfBirth">Date of Birth</label>
            <input type="text" class="form-control" id="dateOfBirth" bind:value="{dateOfBirth}" placeholder="Date of Birth">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="sectors">Sectors</label>
            <input type="text" class="form-control" id="sectors" bind:value="{sectors}" placeholder="Sectors">
          </div>
          <div class="form-group">
            <label class="blue-label" for="industries">Industries</label>
            <input type="text" class="form-control" id="industries" bind:value="{industries}" placeholder="Industries">
          </div>
          <div class="form-group">
            <label class="blue-label"  for="headline">Headline</label>
            <input type="text" class="form-control" id="headline" bind:value="{headline}" placeholder="Headline">
          </div>
          <div class="form-group">
            <label class="blue-label" for="gender">Gender</label>
            <input type="text" class="form-control" id="gender" bind:value="{gender}" placeholder="Gender">
          </div>
          <div class="form-group">
            <label  class="blue-label" for="otherScheduledCaste">Other: Scheduled Caste</label>
            <input type="text" class="form-control" id="otherScheduledCaste" bind:value="{otherScheduledCaste}" placeholder="Other: Scheduled Caste">
          </div>
          <div class="form-group">
            <label class="blue-label" for="GENDER">GENDER</label>
            <input type="text" class="form-control" id="GENDER" bind:value="{GENDER}" placeholder="GENDER">
          </div>

          <!-- Add more form fields here based on your requirements -->

          <button type="submit" class="btn btn-primary">Submit</button>
        </form>
     
 
</main>


    <svelte:head>
	<link
	  rel="stylesheet"
	  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
	/>
  </svelte:head>
  <style>
    .blue-label {
      color: blue;
    }
  </style>
