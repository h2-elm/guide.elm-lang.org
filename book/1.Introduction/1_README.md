# An Introduction to Elm

**Elm is a functional language that compiles to JavaScript.** 

This guide will:
  - Introduce **The Elm Architecture**.
  - Emphasize principles and **patterns** that generalize to programming in any language.

If you give Elm a shot and actually make a project in it, you will end up writing better JavaScript code. 

## A Quick Sample

Here is a little program that lets you increment and decrement a number:

```elm
import Browser
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

main =
  Browser.sandbox { init = 0, update = update, view = view }

type Msg = Increment | Decrement

update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (String.fromInt model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
```

Try it out in the online editor [here](https://elm-lang.org/examples/buttons).

## Why a functional *language*?

There are some things you can only get from a functional *language* like Elm:

  - No runtime errors in practice.
  - Automatically enforced semantic versioning for all Elm packages.

No combination of JS libraries can give you all of these guarantees. They come from the design of the language itself! And thanks to these guarantees, it is quite common for Elm programmers to say they never felt so **confident** while programming. Confident to add features quickly. Confident to refactor thousands of lines. But without the background anxiety that you missed something important!

I have put a huge emphasis on making Elm easy to learn and use, so all I ask is that you give Elm a shot and see what you think. I hope you will be pleasantly surprised!
