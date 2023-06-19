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
	let jobFunction = '';
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
	  // Validate the form data and perform submission logic here
	  // You can access the form field values in the respective variables
	  // e.g., fullName, email, mobile, etc.
	}
  </script>
  
  <main>

		  <form on:submit="{handleSubmit}">
			<div class="form-group">
			  <label for="fullName">Full Name</label>
			  <input type="text" class="form-control" id="fullName" bind:value="{fullName}">
			</div>
			<div class="form-group">
			  <label for="email">Email</label>
			  <input type="email" class="form-control" id="email" bind:value="{email}">
			</div>
			<div class="form-group">
			  <label for="mobile">Mobile</label>
			  <input type="text" class="form-control" id="mobile" bind:value="{mobile}">
			</div>
			<div class="form-group">
			  <label for="candidateCv">Candidate CV</label>
			  <input type="file" class="form-control" id="candidateCv" bind:value="{CandidateCv}">
			</div>
			<div class="form-group">
			  <label for="address">Address</label>
			  <textarea class="form-control" id="address" rows="3" bind:value="{address}"></textarea>
			</div>
			<div class="form-group">
			  <label for="languages">Languages</label>
			  <input type="text" class="form-control" id="languages" bind:value="{languages}">
			</div>
			<div class="form-group">
			  <label for="experience">Experience</label>
			  <input type="text" class="form-control" id="experience" bind:value="{experience}">
			</div>
			<div class="form-group">
			  <label for="qualification">Qualification</label>
			  <input type="text" class="form-control" id="qualification" bind:value="{qualification}">
			</div>
			<div class="form-group">
			  <label for="yearsOfExperience">Years of Experience</label>
			  <input type="text" class="form-control" id="yearsOfExperience" bind:value="{yearsOfExperience}">
			</div>
			<div class="form-group">
			  <label for="industry">Industry</label>
			  <input type="text" class="form-control" id="industry" bind:value="{industry}">
			</div>
			<div class="form-group">
			  <label for="jobFunction">Job Function</label>
			  <input type="text" class="form-control" id="jobFunction" bind:value="{jobFunction}">
			</div>
			<div class="form-group">
			  <label for="dbsCheck">DBS Check</label>
			  <input type="text" class="form-control" id="dbsCheck" bind:value="{dbsCheck}">
			</div>
			<div class="form-group">
			  <label for="fullNRICFINPassportNumber">Full NRIC/FIN/Passport Number</label>
			  <input type="text" class="form-control" id="fullNRICFINPassportNumber" bind:value="{fullNRICFINPassportNumber}">
			</div>
			<div class="form-group">
			  <label for="dateOfBirth">Date of Birth</label>
			  <input type="text" class="form-control" id="dateOfBirth" bind:value="{dateOfBirth}">
			</div>
			<div class="form-group">
			  <label for="sectors">Sectors</label>
			  <input type="text" class="form-control" id="sectors" bind:value="{sectors}">
			</div>
			<div class="form-group">
			  <label for="industries">Industries</label>
			  <input type="text" class="form-control" id="industries" bind:value="{industries}">
			</div>
			<div class="form-group">
			  <label for="headline">Headline</label>
			  <input type="text" class="form-control" id="headline" bind:value="{headline}">
			</div>
			<div class="form-group">
			  <label for="gender">Gender</label>
			  <input type="text" class="form-control" id="gender" bind:value="{gender}">
			</div>
			<div class="form-group">
			  <label for="otherScheduledCaste">Other Scheduled Caste</label>
			  <input type="text" class="form-control" id="otherScheduledCaste" bind:value="{otherScheduledCaste}">
			</div>
			<div class="form-group">
			  <label for="GENDER">GENDER</label>
			  <input type="text" class="form-control" id="GENDER" bind:value="{GENDER}">
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
  