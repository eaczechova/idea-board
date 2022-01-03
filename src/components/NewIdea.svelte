<script>
  let fields = { ideaName: "" };
  let errors = { ideaName: "" };
  let valid = false;

  const submitHandler = () => {
    valid = true;
    if (fields.ideaName.trim().length < 5) {
      valid = false;
      errors.ideaName = "Idea name must be at least 5 characters long.";
    } else {
      errors.ideaName = "";
    }

    if (valid) {
      console.log(fields.ideaName, errors.ideaName);
    }
  };
</script>

<form on:submit|preventDefault={submitHandler}>
  <div class="form-field">
    <label for="idea-type">Type of Ideas</label>
    <input type="text" id="idea-type" bind:value={fields.ideaName} />
    <div class="error">{errors.ideaName}</div>
  </div>
  <button>Add</button>
</form>

<style>
  .error {
    color: red;
  }
</style>
