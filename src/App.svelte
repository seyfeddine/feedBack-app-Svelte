
<script>
import FeedbackList from './componenets/FeedbackList.svelte'
import FeedbackStats from './componenets/FeedbackStats.svelte'
import FeedbackForm from './componenets/FeedbackForm.svelte'

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



 
 const addFeedback = (e) => {
  const newFeedback = e.detail
  feedback = [newFeedback, ...feedback]
 }
</script>

<main class="container">
	<FeedbackForm on:add-feedback={addFeedback}/>
	<FeedbackStats/>
	<FeedbackList />
	
</main>

