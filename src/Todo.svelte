<script>
  import { getContext } from "svelte";
  let some = getContext("key");
  console.log(some);
  export let text;
</script>

<li>
  {text}
</li>

<style>
  li {
    list-style: none;
  }
</style>
