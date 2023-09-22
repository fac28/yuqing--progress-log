## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
> **Make HTML elements look different on hover and focus to indicate their state to the user**  

```
/* Hover effect on .button elements */
.button:hover {
  box-shadow: 2px 2px 2px var(--secondary-dark);
  color: var(--primary-light);
  transform: scale(1.1);
  background-color: rgb(194, 129, 9);
}
```
In this part of our code, we implemented hover styles for elements with the class .button. When users hover over these elements, they experience a change in box-shadow, text color, scale transformation, and background color. This visual feedback provides an indication to the user that the element is interactive and can be clicked.

```
/* Hover effect on .punch elements */
.punch:hover::before {
  opacity: 1;
}
```
Additionally, we defined hover styles for elements with the class .punch. When users hover over the 'punch line' button, a punch emoji is revealed by changing its opacity. This adds a playful and interactive hover effect.

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> **Write user stories with clearly defined acceptance criteria**

While we managed to meet all the requirements given in the Acceptance Criteria, we did not write our own user stories or refined them to include the features our project has.

We could include something like: "As a humor enthusiast, I want to vote up or down jokes and see posts sorted in popularity (with the best ones on top) so that I can easily find and enjoy the funniest content while actively participating in the community's content ranking".

Having this user story defined at the beginning of the project could have better guided our development and enhanced user-centric design. 

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
