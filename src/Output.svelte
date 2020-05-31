<script>
  export let heading

  $: {
    console.log(`exclamation mark ${heading.includes('!') ? '' : 'not '}found`)
  }

</script>

<h1 class:red={heading.includes('!')} >{heading}</h1>

<style>
.red {
  color: red;
}
</style>