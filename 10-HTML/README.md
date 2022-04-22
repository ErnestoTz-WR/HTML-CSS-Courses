# HTML

## Template

The `<template>` HTML element is a mechanism for holding HTML that is not to be rendered immediately when a page is loaded but may be instantiated subsequently during runtime using JavaScript. Think of a template as a content fragment that is being stored for subsequent use in the document.

```HTML
<body>
    <template id="single-post"> <!-- We use an id to get access to the template on JS-->
        <li class="post-item">
        <h2></h2>
        <p></p>
        <button>DELETE</button>
        </li>
    </template>
    <section id="available-posts">
      <button>FETCH POSTS</button>
      <ul class="posts"></ul>
    </section>
</body>
```

```JavaScript
const postTemplate = document.getElementById('single-post');
const listElement = document.querySelector('.posts');

async function fetchPosts() {
    // fetch data function in another file
  const responseData = await sendHttpRequest(
    'GET',
    'https://jsonplaceholder.typicode.com/posts'
  );
  const listOfPosts = responseData;
  for (const post of listOfPosts) { 
      // 1. Make a true copy of the template.
      const postEl = document.importNode(postTemplate.content, true); 
      // 2. Update necessary information
      postEl.querySelector('h2').textContent = post.title.toUpperCase();
      postEl.querySelector('p').textContent = post.body;
      // 3. Attach element to the DOM
      listElement.append(postEl);

      // Since we created a true copy of the template element
      // we did not have to create the list element with the class "post-item" 
  }
}
```