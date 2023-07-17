<script setup>
async function submit(values) {
  await new Promise(r => setTimeout(r, 1000))
  console.log(values)
  alert('Submitted! 🎉')
}
</script>

<template>
  <div class="your-first-form">
    <FormKit type="form" #default="{ value }" @submit="submit">
      <FormKit type="textarea" name="describe" rows='5' label="Experience rating"
        help="How would you describe your experience?" />
      <FormKit name='experience' type='range' label='Rate your experience' min='0' max='10'
        help='Rate your experience from 0 to 10' />
      <FormKit type="textarea" name="favorite" rows='5' label="Favorite parts"
        help="Please explain your favorite parts about this experience." />
      <FormKit type="textarea" name="lessgood" rows='5' label="Least liked parts"
        help="Please explain your less liked parts about this experience." />
      <FormKit type="textarea" name="next" rows='5' label="Things to try"
        help="Tell us what you would like to try next time." />
      <FormKit type="checkbox" name="agree" label="I agree I am providing factual feedback." />
      <pre>{{ value }}</pre>
    </FormKit>
  </div>
</template>

<style scoped>
.your-first-form {
  width: calc(100% - 2em);
  max-width: 480px;
  box-sizing: border-box;
  padding: 2em;
  box-shadow: 0 0 1em rgba(0, 0, 0, .1);
  border-radius: .5em;
  margin: 4em auto;
}

.logo {
  width: 150px;
  height: auto;
  display: block;
  margin: 0 auto 2em auto;
}

pre {
  background-color: rgba(0, 100, 250, .1);
  padding: 1em;
}
</style>
