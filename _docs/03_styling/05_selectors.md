---
title: Selectors
category: Styling
order: 4
---
---
CSS uses selectors to determine which elements the defined properties will affect. The following subsections describe the CSS selector supported by tuix.

# Simple Selectors

## Element Selector (element_name)
Selects elements based on the element name given to them. An element name can be given to widget using the entity id with `entity.insert_element(state, "element_name")`, or using the builder closure with `builder.insert_element("element_name")`. A widget can only have one element name.
##### Example
All buttons will have a blue background color:
```css
button {
    background-color: blue;
}
```

## Class Selector (.class_name)
Selects elements based on the class name given to them. A class name can be given to a widget using the entity id with `entity.class(state, "class_name")`, or using the builder closure with `builder.class("class_name")`. A widget can have multiple class names.

// TODO - Adding, Removing and Replacing class names
##### Example
All widgets with a class name of `item` will have a height of 30 pixels:
```css
.item {
    height: 30px;
}
```

## Universal Selector (*)
The universal selector (*) will select all widgets.
##### Example 
All widgets will have centered text:
```css
* {
    text-justify: center;
}
```

# Combinator Selectors
A combinator can be used between simple slectors to match more specific widgets. There are 2 combinator selectors supported by tuix:

 - descendant selector (space)
 - child selector (>)

## Descendant Selector (space)
Selects all entities that are descendants of a specified entity.
##### Example
All buttons inside of panels will have a flex-grow of 1.0:
```css
panel button {
    flex-grow: 1.0;
}
```

## Child Selector (>)
Selects all entities that are children of a specified entity.
##### Example
All buttons that are children of a panel container will have a red background:
```css
panel.container > button {
    background-color: red;
}
```