# Simple-Jekyll-Search Fork by Vallek

Simple-Jekyll-Search adds search functionality to any Jekyll blog.

This is a fork of now archived [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search) by [@christian-fei](https://github.com/christian-fei) with some added features.

I could only make it work on my sites by manually linking javascript file. The extension is also not supported on GitHub Pages. So I decided to leave only search extension files here since i'm not going to change anything else. 

For demo you can check my [WebDevTips](https://vallek.github.io/webdevtips/) site.

**But you still need to install original npm package for build to work!**

## Added features
* Hides results container when there's no results
* Shows results container on focus, hides on focus lost

So you can style search results container how you want. In original it would show up empty (with borders for example).

## How to install and use

Go to Jekyll project folder in your terminal

```sh
npm install simple-jekyll-search
```

Put search.json in project root folder.

**search.json** defines what will be searched (titles, tags, content) and creates json "data base" on build. My version comes with content search enabled.

Link both javascript files from js folder to your page. This is how it looks on my project: 

```html
<script defer src="{{site.baseurl}}/js/simple-jekyll-search.js"></script>
<script defer src="{{site.baseurl}}/js/search.js"></script>
```
**simple-jekyll-search.js** is the search code base itself with new features.

I'm using `visually-hidden` css class there to visually hide results. Add this to your CSS:
```
.visually-hidden {
  border: 0;
  clip: rect(0 0 0 0);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}
``` 

**search.js** is the options you can tweak:
```js
// id of search input
searchInput: document.getElementById('search-input'),
    // id of results container
		resultsContainer: document.getElementById('results-container'),
    // path to search.json
		json: './search.json',
    // html for results
		searchResultTemplate: '<li class="search__item"><a class="search__link" href="{url}">{title}</a></li>',
    // text if nothing was found
		noResultsText: 'No results found',
    // Max results
		limit: 10,
    // Fuzzy search
		fuzzy: false,
```
You can change all of that if needed. I found fuzzy to be not very helpful. At least without more details in search results (which may be coming). 

Altogether you need to add 3 (three) files to your project + install npm modules.

## Styling
This comes without any styles (for now at least). You can try to use mine from [Web Dev Tips](https://github.com/Vallek/webdevtips/blob/master/_sass/minima/_layout.scss#LL135C1-L135C10).

If you have problem please try to search [original repo](https://github.com/christian-fei/Simple-Jekyll-Search/issues?q=is%3Aissue+is%3Aclosed) and [readme](https://github.com/christian-fei/Simple-Jekyll-Search#readme) first. And then you can ask here of course)  

Thanks to [@christian-fei](https://github.com/christian-fei) for his work.

## Contributors (from original repo readme)

Thanks to all [contributors](https://github.com/christian-fei/Simple-Jekyll-Search/graphs/contributors) over the years! You are the best :)

> [@daviddarnes](https://github.com/daviddarnes)
[@XhmikosR](https://github.com/XhmikosR)
[@PeterDaveHello](https://github.com/PeterDaveHello)
[@mikeybeck](https://github.com/mikeybeck)
[@egladman](https://github.com/egladman)
[@midzer](https://github.com/midzer)
[@eduardoboucas](https://github.com/eduardoboucas)
[@kremalicious](https://github.com/kremalicious)
[@tibotiber](https://github.com/tibotiber)
and many others!

