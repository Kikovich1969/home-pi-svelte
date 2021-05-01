<script>
  import { onMount } from "svelte";
  let date = new Date();
  $: hour = date.getHours();
  $: min = date.getMinutes();
  $: sec = date.getSeconds();

  onMount(() => {
    const interval = setInterval(() => {
      date = new Date();
    }, 1000);
  });
</script>

<div>{hour} : {min < 10 ? `0${min}` : min} : {sec < 10 ? `0${sec}` : sec}</div>

<style>
  div {
    text-align: center;
  }
</style>
