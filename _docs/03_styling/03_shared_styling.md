---
title: Shared Styling
category: Styling
order: 3
---
---

## Reloadable Stylesheet
To add a stylesheet to an app, simply call `state.add_stylesheet("path_to_stylesheet.css")`, where `path_to_stylesheet.css` is replaced by the path and name of the `.css` file you wish to include. Adding stylesheets in this way allows for hot reloading in which changes can be made to the stylsheets while the application is running and can be refreshed by pressing the `F5` key.


## Embedded Stylesheet
An alternative way to include a stylesheet is by using the `include_str!` macro. For example:
```rs
static THEME: &'static str = include_str!("path_to_stylesheet.css");

// Inside the app
state.insert_theme(THEME);
```
This includes the contents of the stylesheet in the application binary itself and so cannot be hot reloaded. This is useful if you do not want the user of your apps to be able to modify the stylesheet properties.