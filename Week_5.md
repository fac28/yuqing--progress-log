## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/client-side-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Use function components to organise our code**  
 We used components for different buttons:

```JavaScript
<div className="card buttons">
   <Sleep {...actionProps} />
   <Coding {...actionProps} />
   <Coffee {...actionProps} />
   <Apply {...actionProps} />
</div>
```

This worked well because Shaughn and I sometimes work on improving different functions, and it won't cause conflicts.

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Use component state to manage DOM updates**
We (mostly I) abused useReducer, it's not really needed here. Alphonso's suggestion on using useEffect was helpful:

```JavaScript
export default function checkPulse(stats){
	let cause = ''
	
	if(stats.age > 49) cause = 'being too old'
	if(stats.coffee > 9) cause = 'too much coffee'
	// etc ...
	return cause
}
```

```JavaScript
useEffect(()=>{
	const cause = checkPulse(stats)
	if (cause !== ''){
		setAlive(false)
		setDeathCause(cause)
	}
}, [age, energy])
```

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
