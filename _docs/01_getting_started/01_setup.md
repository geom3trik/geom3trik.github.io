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

Also inside the `my_tuix_app` directory should be a sub-directory called `src`, and inside this sub-directory there should be a file called `main.rs`. This is the starting point for a Rust application and where we will start writing our first tuix application.

