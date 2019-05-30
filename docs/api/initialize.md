### initialize method

```js
FlowRouter.initialize(options);
```

- `options` {*Object*}
  - `hashbang` {*Boolean*} - Enable hashbang urls like `mydomain.com/#!/mypath`, default: `false`
  - `page` {*Object*} - Options for [page.js](https://github.com/visionmedia/page.js#pageoptions)
    - `click` {*Boolean*} - When false, `<a href>` tags in your app won't automatically call flow router and will do the browser's default page load instead. This is identical to how `react-router` behaves. You can create a `<Link />` component that calls `FlowRouter.go` in its `onClick` handler. This way, you have more control over your links. Default: `true`
    - Other options can be found in a [`page.js` docs](https://github.com/visionmedia/page.js#pageoptions)
- Returns {*void*}

By default, FlowRouter initializes the routing process in a `Meteor.startup()` callback. This works for most of the applications. But, some applications have custom initializations and FlowRouter needs to initialize after that.

So, that's where `FlowRouter.wait()` comes to save you. You need to call it directly inside your JavaScript file. After that, whenever your app is ready call `FlowRouter.initialize()`.

#### Example

```js
FlowRouter.wait();
WhenEverYourAppIsReady(() => {
  FlowRouter.initialize();
});
```

#### Further reading

- [`.wait()` method](https://github.com/VeliovGroup/flow-router/blob/master/docs/api/wait.md)
