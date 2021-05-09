<script>
  let name;
  let beltColor;
  let age;

  let skills = [];

  const handleSubmit = () => {
    console.log(name, beltColor, age, skills);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="Name" bind:value={name} />
  <input type="number" placeholder="Age" bind:value={age} />
  <label>Skills:</label>
  <input type="checkbox" bind:group={skills} value="fighting" />fighting<br />
  <input type="checkbox" bind:group={skills} value="runing" />Runing<br />
  <input type="checkbox" bind:group={skills} value="sneaking" />Sneaking<br />
  <label>Belt Color:</label>
  <select bind:value={beltColor}>
    <option value="white">White</option>
    <option value="yellow">Yellow</option>
    <option value="green">Green</option>
    <option value="blue">Blue</option>
    <option value="brown">Brown</option>
    <option value="black">Black</option>
  </select>
  <button>Add Person</button>
</form>

<style></style>
