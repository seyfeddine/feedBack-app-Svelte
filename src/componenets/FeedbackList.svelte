<script> 
// import {onMount, onDestroy} from 'svelte'
import {FeedbackStore} from '../stores'
import { fade, scale } from 'svelte/transition'
import FeedbackItem from "./FeedbackItem.svelte";
// let feedback = []
// const unsebscribe = FeedbackStore.subscribe((data) =>feedback = data )

// onMount(() => {
//     console.log('mounted');
// })

// onDestroy(() => {
//     unsebscribe()
// })

/////////Another way to get the store data use directly $FeedbackStore and it unsebscribe directly

 
</script>


{#each $FeedbackStore as fb (fb.id)}
<div in:scale out:fade="{{ duration: 500 }}">
    <FeedbackItem item={fb} />
</div>

{/each}