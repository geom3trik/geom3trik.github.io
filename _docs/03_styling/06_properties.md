---
title: Properties
category: Styling
order: 6
---
---

This page presents a comprehensive list of style properties supported by tuix.

| Property                   | Value Type                                                                               | Default Value | Animatable | Setter                              |
|----------------------------|------------------------------------------------------------------------------------------|---------------|------------|-------------------------------------|
| display                    | None \| Flex                                                                             | Flex          | No         | `.set_display()`                    |
| visibility                 | Visible \| Invisible                                                                     | Visible       | No         | `.set_visibility()`                 |
| opacity                    | Opacity(f32)                                                                             | Opacity(1.0)  | Yes        | `.set_opacity()`                    |
| position                   | Relative \| Absolute                                                                     | Relative      | No         | `.set_position()`                   |
| left                       | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_left()`                       |
| right                      | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_right()`                      |
| top                        | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_top()`                        |
| bottom                     | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_bottom()`                     |
| width                      | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_width()`                      |
| height                     | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_height()`                     |
| max-width                  | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_max_width()`                  |
| min-width                  | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_min_width()`                  |
| max-height                 | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_max_height()`                 |
| min-height                 | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_min_height()`                 |
| margin                     | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_margin()`                     |
| margin-left                | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_margin_left()`                |
| margin-right               | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_margin_right()`               |
| margin-top                 | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_margin_top()`                 |
| margin-bottom              | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_margin_bottom()`              |
| padding                    | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_padding()`                    |
| padding-left               | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_padding_left()`               |
| padding-right              | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_padding_right()`              |
| padding-top                | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_padding_top()`                |
| padding-bottom             | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_padding_bottom()`             |
| border-width               | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_width()`               |
| border-color               | Color                                                                                    | rgba(0,0,0,0) | Yes        | `.set_border_color()`               |
| border-radius              | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_radius()`              |
| border-radius-top-left     | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_radius_top_left()`     |
| border-radius-top-right    | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_radius_top_right()`    |
| border-radius-bottom-left  | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_radius_bottom_left()`  |
| border-radius-bottom-right | Pixels \| Percentage \| Auto \| Initial                                                  | 0px           | Yes        | `.set_border_radius_bottom_right()` |
| background-color           | Color                                                                                    | rgba(0,0,0,0) | Yes        | `.set_background_color()`           |
| background-image           | None \| String \| LinearGradient \| RadialGradient                                       | None          | No         | `.set_background_image()`           |
| flex-direction             | Row \| Column                                                                            | Column        | Yes        | `.set_flex_direction()`             |
| justify-content            | FlexStart \| FlexEnd \| Center \| Stretch \|  SpaceBetween \| SpaceAround \| SpaceEvenly | FlexStart     | No         | `.set_justify_content()`            |
| align-items                | FlexStart \| FlexEnd \| Center \| Stretch                                                | Stretch       | No         | `.set_align_items()`                |
| align-content              | FlexStart \| FlexEnd \| Center \| Stretch \| SpaceBetween \| SpaceAround                 | FlexStart     | No         | `.set_align_content()`              |
| align-self                 | FlexStart \| FlexEnd \| Center \| Stretch                                                | Stretch       | No         | `.set_align_self()`                 |
| flex-grow                  | f32                                                                                      | 0.0           | Yes        | `.set_flex_grow()`                  |
| flex-shrink                | f32                                                                                      | 0.0           | Yes        | `.set_flex_shrink()`                |
| flex-basis                 | Pixels \| Percentage \| Auto \| Initial                                                  | 0.0           | Yes        | `.set_flex_basis()`                 |
| text-justify               | Start \| Center \| End                                                                   | Start         | No         | `.set_text_justify()`               |
| text-align                 | Start \| Center \| End                                                                   | Center        | No         | `.set_text_align()`                 |
| font                       | String (fontID)                                                                          |               | No         | `.set_font()`                       |
| color                      | Color                                                                                    | rgba(0,0,0,0) | Yes        | `.set_font_color()`                 |
| font-size                  | f32                                                                                      |               | Yes        | `.set_font_size()`                  |

# Display
The `display`, `visibility`, and `opacity` properties are used to determine whether an element is shown.

## position
- **Value:** `relative || absolute`
- **Default Value:** `relative`
- **Animatable:** No
- **Rust Type:** `Position`
- **Setter Example:** `.set_position(state, Position::Relative)`


# Positioning
The `top`, `bottom`, `left` and `right` properties are used with the `postition` property to place an entity.

## position
- **Value:** `relative || absolute`
- **Default Value:** `relative`
- **Animatable:** No
- **Rust Type:** `Position`
- **Setter Example:** `.set_position(state, Position::Relative)`

## top
- **Description:** The desired position of the element measured from the top.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** auto
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_top(state, Length::Pixels(100.0))`

## bottom
- **Description:** The desired position of the element measured from the bottom. Is overriden by `top` property. 
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_left(state, Length::Pixels(100.0))`

## left
- **Description:** The desired position of the element measured from the left.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** auto
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_left(state, Length::Pixels(100.0))`

## right
- **Description:** The desired position of the element measured from the right. Is overriden by `left` property. 
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_right(state, Length::Pixels(100.0))`

# Size 
The `width` and `height` properties are used to set the desired width and height of an element.

## width
- **Description:** The desired width of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_width(state, Length::Pixels(100.0))`

## height
- **Description:** The desired height of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_height(state, Length::Pixels(100.0))`

# Margins
Margins determine the space around an entity.

## margin
- **Description:** The desired margins of the element. Sets `margin-left`, `margin-right`, `margin-top`, and `margin-bottom` to the desired value.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_margin(state, Length::Pixels(100.0))`

## margin-top
- **Description:** The desired top margin of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_margin_top(state, Length::Pixels(100.0))`

## margin-bottom
- **Description:** The desired bottom margin of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_margin_bottom(state, Length::Pixels(100.0))`

## margin-left
- **Description:** The desired left margin of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_margin_left(state, Length::Pixels(100.0))`

## margin-right
- **Description:** The desired right margin of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_margin_right(state, Length::Pixels(100.0))`

# Padding
Padding determines the space between an entity and its contained children.

## padding
- **Description:** The desired padding of the element. Sets `padding-left`, `padding-right`, `padding-top`, and `padding-bottom` to the desired value.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_padding(state, Length::Pixels(100.0))`

## padding-top
- **Description:** The desired top padding of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_padding_top(state, Length::Pixels(100.0))`

## padding-bottom
- **Description:** The desired bottom padding of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_padding_bottom(state, Length::Pixels(100.0))`

## padding-left
- **Description:** The desired left padding of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_padding_left(state, Length::Pixels(100.0))`

## padding-right
- **Description:** The desired right padding of the element.
- **Value Type:** `<length> || <percentage> || intial || auto`
- **Default Value:** `auto`
- **Animatable:** Yes
- **Rust Type:** `Length`
- **Setter Example:** `.set_padding_right(state, Length::Pixels(100.0))`

