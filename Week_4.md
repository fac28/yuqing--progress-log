## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server-side-app/schedule/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### **1. Show evidence of a learning outcome you have achieved this week.**
**Research and implement complex new features on our own**  

This week I contributed to two stretch goal features: filtering by tags and adding buttons to delete images. Here I will focus on the filtering feature.

**Part 1: Adding tags**

We first went to the schema to add a new 'tags' column in out image_details table. It stores the tag(s) of each picture as a string (e.g. '' for no topic; 'travel, fantasy' for a picture tagged with two topics. Then we went on to create a new field in our form:

```html
 <fieldset>
  <legend>Please select one or more of the following tags</legend>

  ${filterCategories.map(filter => `
    <input type="checkbox" name="action[]" id="${filter}" value="${filter}" />
    <label for="${filter}">${filter}</label>
    `).join("")}

</fieldset>
```

When a user submits the form, we convert the array of tag(s) into a string, and inserted into the image_deatails table:

```javascript
let tags = req.body.action;

// this is to handle the case where no tag is selected
if (!tags) {
  tags = [];
}

const tagsString = tags.join(", ");
insertArtworkDetails(tagsString, other-stuff);

```

**Part 2: Display filtered results**

We used css to hide and show images with certian tags. I really enjoyed writing the filter.js:

```javascript
const imageContainers = document.querySelectorAll(".gallery-child");

// check if the image contains __any__ of the selected tag
function isTagged (tags, userFilter) {
  return tags.split(", ").some(function (tag) {
    return tag === userFilter;
  });
}

function hideImage (userFilter) {
  let allHidden = true;

  ...

  imageContainers.forEach(function (imageContainer) {
   // getting the tag seleced by user
    const tags = imageContainer.querySelector(".main__tags").innerText;

  // un-hide the images with the current tag
    if (isTagged(tags, userFilter) === true) {
      imageContainer.setAttribute("hidden", false);
      allHidden = false;
    } else {
      // hide the other images
      imageContainer.setAttribute("hidden", true);
    }
  });

  // display a message if there's no image having that tag
  if (allHidden) {
    const p = document.createElement("p");
    p.className = "main__no-images";
    p.innerText = "No images found";
    const main = document.querySelector("main");
    main.appendChild(p);
  }
}
```

and in our css, we have:

```css
[hidden='true'] {
  display: none;
}

[hidden='false'] {
  display: block;
}
```

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Build a stable, professional app**

Our deployed app keeps on crashing during the code review because of memory issues. We were able to spot the problem by reading Sentry logs, but we don't really have a solution for it now. On the last day, I added a function to limit the size of images, which should be helping, but our deployed app is still crushing. Hopefully in coming weeks we'll learn a better way to store larger files like images.

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
