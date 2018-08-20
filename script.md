# This script can be used to retrieve authors published articles.

## Caveats - 

* This script needs to be run in Browser Console.

## Steps - 

* Go to https://medium.com/me/stats?format=json.
* Open Browser Console with `Ctrl + Shift + J` in Chrome.
* Execute this code. (change author_name with yours).

```js
author_name = 'adityaa803'
raw_data = document.body.querySelector('pre').innerHTML
data = JSON.parse(raw_data.substring(22))
content = ''
posts = data.payload.value
posts.sort((a, b) => b.views - a.views)
posts.forEach(post => {
  content += `\n\n1. [${post.title}](https://medium.com/@${author_name}/${post.slug}-${post.postId})`
})
console.log(content)
copy(content)
```
