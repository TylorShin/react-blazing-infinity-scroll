# react-intersection-observing-infinity-scroll [![GitHub Starts](https://img.shields.io/github/stars/TylorShin/react-intersection-observing-infinity-scroll.svg)](https://github.com/TylorShin/react-intersection-observing-infinity-scroll) [![GitHub contributors](https://img.shields.io/github/contributors/TylorShin/react-intersection-observing-infinity-scroll.svg)](https://github.com/TylorShin/react-intersection-observing-infinity-scroll/graphs/contributors/) [![Node version](https://img.shields.io/badge/Node-8+-green.svg)](https://nodejs.org/) [![React Version](https://img.shields.io/badge/React-16%2B-green.svg)](https://reactjs.org/)

![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![IE](https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png) | ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png)
--- | --- | --- | --- | --- |
 ✔ |  ✔ | 9+ ✔ |  ✔ |  ✔ |

[example page](https://tylorshin.github.io/react-intersection-observing-infinity-scroll/example)

React component that supports infinity scroll with tiny size (< 3kb without gzip)  
It supports SSR build and fallback render with `<div>` element.  

This library doesn't use any `eventListener` for scroll event. Rather than eventListener, It uses [Intersection Obeserver API] (https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API). 
 This is the reason why you need polyfill.

Also, this library is written in TypeScript.  

## Before install
You should install [intersection Observer polyfill](https://github.com/w3c/IntersectionObserver/tree/master/polyfill).  
You can choose all possible ways to install the polyfill, however the polyfill **MUST** comes before the library script.  
I think you can optimize polyfill strategy like [Polyfill.io](https://polyfill.io/v2/docs/).  

example
```
<!-- Load the polyfill first. -->
<script src="path/to/intersection-observer.js"></script>

<!-- Load all other JavaScript. -->
<script src="react-intersection-observing-infinity-scroll.js"></script>
```

## How to install
**IMPORTANT**  
You should install `intersection Observer` polyfill to support IE & elder browsers.
```
$ npm install -S react-intersection-observing-infinity-scroll

```

## How to use
```
<InfiniteScroll
  loadMoreFunc={loadMore}
  isLoading={isLoading}
  hasMore={!isEnd}
  loaderComponent={<div className="loader">{this.renderLoadingSpinner()}</div>}
>
  {/* list content */}
</InfiniteScroll>
```

If you want to see detail implementation, visit [example page](https://tylorshin.github.io/react-intersection-observing-infinity-scroll/example) and code.

## To Do

- [x] Support server side build for Universal rendering.
- [ ] Support `position: fixed` user custom loading component.
- [ ] Support Reverse direction infinite scrolling.
- [ ] Hide invisible items with some buffer for the performance enhancement.
