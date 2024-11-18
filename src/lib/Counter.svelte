<script>
  let count = $state(0)
  const increment = () => {
    if (count < 20) {
      count += 1
    }
  }
  const decrement = () => {
    if (count > 0) {
      count -= 1
    }
  }
</script>

<div>
  Contador: {count} 
</div>

<button onclick={increment}>
  Increment
</button>

<button onclick={decrement}>
  Decrement
</button>