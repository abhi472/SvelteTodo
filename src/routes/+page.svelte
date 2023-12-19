<p></p>
<button on:click={increment}>click</button>

<p>
    Clicked {count} {count === 1 ? 'time': 'times'}
</p>

<script>
import { onMount } from 'svelte';
let count = 0;
function increment() {
    count += 1;
}



</script>