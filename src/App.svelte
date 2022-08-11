
<script>
import FeedbackList from './componenets/FeedbackList.svelte'
import FeedbackStats from './componenets/FeedbackStats.svelte'

let feedback = 
	[
  {
    id: 1,
    rating: 10,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 2,
    rating: 9,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 3,
    rating: 8,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
]

$: count = feedback.length
$: average = feedback.reduce((a, {rating})=> a + rating, 0 )/count

 const deleteFeed = (e) =>{
	const itemId = e.detail 
	feedback = feedback.filter((item)=> item.id != itemId )
 }
</script>

<main class="container">
		<FeedbackStats	{count} {average}/>
	<FeedbackList feedback={feedback} on:delte-feed={deleteFeed}/>
	
</main>

