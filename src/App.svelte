<script>
  import Modal from "./Modal.svelte";
  import AddPersonForm from "./AddPersonForm.svelte";

  let pepole = [
    { name: "yoshi", beltColor: "Black", age: 30, id: 1 },
    { name: "ken", beltColor: "Blue", age: 17, id: 2 },
    { name: "Ikagura", beltColor: "Orange", age: 10, id: 3 },
  ];

  const deletePerson = (id) => {
    pepole = pepole.filter((person) => person.id != id);
  };

  let showModal = true;
  //   modal handler
  const handleModal = () => {
    showModal = !showModal;
  };
</script>

<Modal {showModal} on:click={handleModal}>
  <h3>Add person</h3>
  <AddPersonForm />
</Modal>
<main>
  <button on:click={handleModal}>Open Modal</button>
  {#each pepole as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColor === "Black"}
        <p><strong>Master</strong></p>
      {/if}
      <p>{person.age} Year old, {person.beltColor} Belt.</p>
      <button on:click={() => deletePerson(person.id)}>Delete</button>
    </div>
  {:else}
    <div>No pepole to show.....</div>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h4 {
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
