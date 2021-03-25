---
layout: page
title: Setup
category: Getting Started
order: 1
---
---


## Creating a Tuix App

### Create a new Rust binary executable project
Navigate to the folder where you would like to create your project and then run the following command:

```
cargo new my_tuix_app
```

This will create a new directory called `my_tuix_app` which will contain the source files for your project. Navigate into this directory and add the following dependency to the `cargo.toml` file in your favourite code editor. 

```
tuix = {git = "https://github.com/geom3trik/tuix", branch = "main"}
```


