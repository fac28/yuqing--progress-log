## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/authentication/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Run tests and linter in CI to prevent broken code reaching the main branch**  

We chained two workflows to make sure that tests are passed (when "Node.js CI" is completed) before deployment can happen:

```
name: Fly Deploy
on:
  workflow_run:
    workflows: ["Node.js CI"]
    types:
      - completed
jobs:
  deploy:
    name: Deploy app
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: superfly/flyctl-actions/setup-flyctl@master
      - run: flyctl deploy --remote-only
        env:
          FLY_API_TOKEN: ${{ secrets.FLY_API_TOKEN }}
```


 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Ensure only authenticated users can see certain content**
Currently we are onling showing the events created by the current user without giving them the option to see anything more. 

```
const select_events = db.prepare(/*sql*/ `
SELECT 
  content, 
  event_date
FROM events
WHERE user_id = ?
ORDER BY event_date
`);

function listEvents(user_id) {
  return select_events.all(user_id);
}
```

It will be nice to show the user more events, but only allow deletion by the current user. 

## Feedback
### Alphonso's Feedback
#### What Went Well
Your example to the first question is great! Maybe think of adding a little bit detail on the testing you are running there as well.
This example is something a few learners struggled with this week so it would be nice to use one of the chances for large group discussion (live code review or circle roles maybe) to share these learnings with the others.

#### Even Better If
The jump to allow specific actions, like deleting content, only to signed-in users is not very big from the logic you already have there.
Here's a snippet from a project my cohort worked on:

```javascript
function entriesPage(entries, userId, userName) {
  const entryList = entries
    .map(
      (entry) => /*html*/ `
    <div class="entry-post stack-sm">
      <div class="entry-post__header no-top-margin row space-between">
        <p>
          ${entry.posted_at}
          <span class="entry-post__header${
            userId === entry.user_id ? `--user-name` : `--anonymous`
          }">
            ${userId === entry.user_id ? userName : 'anonymous'}
          </span>
        </p>
        <form action='/entries/delete/${entry.id}' method='post'>
          <button class="entry-post__delete-button ${
            userId === entry.user_id ? `row` : `hidden` // HERE you only get to see the delete button at all if you are signed in
          }"> X </button>
        </form>
      </div>
      <div class="entry-post__body">
        ${entry.content}
      </div>
    </div>`
    )
    .join('');
```

The project is called [t33n-ang5t](https://github.com/fac27/t33n-ang5t), you can have a look through for a few more simple functionalities running on this logic.
