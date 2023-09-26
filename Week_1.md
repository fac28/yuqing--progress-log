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
### **Alphonso's feedback:**
#### *What went well*
Your examples of changing the look of buttons show a lot of focus on the user experience! The changes to your buttons are very commonly understood to mean that something is clickable and will easily guide users when interacting with the page. The emoji example is particularly creative and does the same job while creating a sense of 'identity' for your page. Top stuff!

Your examle of a user story is actually very good, if maybe a little too descriptive. It's great if you start applying this thinking to projects from now, but you also have the opportunity to explore user stories in much more depth as we work through the *Tech for Better* program, where the definition process is much more guided.

#### *Even better if*
Keep the naming of your elements in mind. Particularly, consider the scalability of these naming practices. Right now you are working in 2-day sprints and projects don't grow to very large proportions, but they will very soon. When you have a very large codebase, the name 'button' or 'punch' won't help much and might actually get confusing.
This may seem counterintuitive because we try to reduce noise in the code by being less verbose, but a more descriptive name can help you identify what you are working with later on, or if you are a new developer joining the project. For example, ```.punchline-button``` instead of ```.punch```
