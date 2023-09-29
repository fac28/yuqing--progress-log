## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/database/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Create, read update and delete from our database using SQL queries**  

While I have worked with SQL queries before, this week is the first time I get to create, update and delete from a database.

The following code example shows how I combined querying the database to find if a customer is existing, and then adding a new entry to the database if it's missing.

```
function createCustomer (customer) {
  const { ownerID } = findOwnerId(customer.owner_name)

  if (isRegistered(customer.dog_name, customer.owner_name) === false) {
    console.log('registering you now')

    return addCustomer.run({
      name: customer.dog_name,
      breed: customer.breed,
      owner: ownerID
    })
  }
}
```

We could create a similar function to prevent duplicated bookings in the future.

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
 **Set enviroment variables and understand their use case**

I didn't have a good understanding of the need to do this, and hardcoded db.js to read from db.sqlite so we can avoid an error one teammate had on Windows. This has caused issues with deployment.

 We changed it to:
 ```
 const db = new Database(process.env.DB_FILE || 'db.sqlite')
 ```
 so that the following script can be ran:
 ```
 "seed-fly": "DB_FILE=/data/db.sqlite node database/seed.js"
 ```

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
