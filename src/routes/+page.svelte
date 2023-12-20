<p></p>
<button on:click={increment}>click</button>

<p>
    {list}
</p>

<p> Amount is {amount}</p>

<script>
let list = ['a', 'b', 'c', 'd'];
// let amount = list.length; this is not gonna update itself
$: amount  = list.length;
 
function increment() {

    // list.push('e');
    // list = list;

    //we can update the upper code as 
    list = [...list, 'e'];
}




</script>