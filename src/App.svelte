<script>
  import { setContext } from "svelte";
  import Todo from "./Todo.svelte";
  let any = { name: "husnain" };
  setContext("key", any);

  let array = [];
  let text = "";
  function addContent() {
    array = [...array, text];
    text = "";
  }
</script>

<div class="container">
  <main>
    <ul>
      {#each array as a}
        <Todo text={a} />
      {/each}
    </ul>
    <div class="inputContainer">
      <input type="text" bind:value={text} />
      <button on:click={addContent}>Add</button>
    </div>
  </main>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
  }
  .container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  main {
    padding: 20px;
    width: 450px;
    min-height: 100px;
  }
  input {
    width: 300px;
    height: 40px;
    padding-left: 5px;
  }
  button {
    width: 120px;
    height: 40px;
    cursor: pointer;
    font-size: larger;
    font-weight: 600;
  }
</style>
