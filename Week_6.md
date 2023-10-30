## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/full-stack-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Learn new technology from external resources/documentation**  
Dynamic Routes with Next 13 is a challenging one to learn. Here is the folder structure we had in the end:

<img width="474" alt="image" src="https://github.com/fac28/yuqing--progress-log/assets/44486576/09a1ddea-d00b-434d-82f4-46d8a7baaa1f">

so products/1/1 points to a white airpod, products/1/2 points to a black airpod, and products/2 points to a t-shirt

Ideally a route like ```products/[product_name]colour=white&size=M``` would make better sense.

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Use the Next.js framework to make server-rendered React apps**

In this project we used one component for each page. In the future, we can have components for reusable elements like Navbar and Footer like this:

```JavaScript
import Link from 'next/link'

export default function Navbar() {
  return (
    <nav>
      <Link
        className="home"
        href="/"
      >
        <h1>Unwanted Crap</h1>
      </Link>
      <div className="basket">
        <Link href="/basket">
          Basket
        </Link>
      </div>
    </nav>
  )
}
```


## Feedback
> Beth

> You've demonstrated a good understanding of how to implement dynamic routes in Next.js 13, as well as the folder structure required to make it work. Your example of a Navbar component is well-structured, and it’s good that you’re thinking about how to organise your code for future projects.
 
> To play around with creating API routes on Next, begin experimenting with creating API routes in a small, controlled environment. Here’s a [simple tutorial on API routes in Next.js to get you started](https://nextjs.org/docs/app/building-your-application/routing).
