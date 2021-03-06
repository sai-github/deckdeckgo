# Background

Beside slides and templates, a [DeckDeckGo] deck could also contain a customized element `background` which could be injected using a dedicated `slot`.

## Table of contents

- [Introduction](#app-deck-background-introduction)
- [Attributes](#app-deck-background-attributes)
- [Theming](#app-deck-background-theming)
- [Examples](#app-deck-background-examples)

## Introduction

The slot `background` provided for the deck will be cloned into each slides of your presentation.

Optionally, if you wish, this slot could also not be cloned, could be useful in case you rather would like to display a background which follows your entire presentation.

## Attributes

The following attribute could be applied to the `deckgo-deck` element:

| Property          | Attribute          | Mandatory | Description                                                                | Type      | Default |
| ----------------- | ------------------ | --------- | -------------------------------------------------------------------------- | --------- | ------- |
| `cloneBackground` | `clone-background` |           | Set to false in case you don't want to clone the background in each slides | `boolean` | true    |

## Theming

The following theming options will affect the slot `background` if set on the `deckgo-deck` or any slides.

| CSS4 variable                    | Default  | Note                                                      |
| -------------------------------- | -------- | --------------------------------------------------------- |
| --slide-background-position      | absolute | The position of the background                            |
| --slide-background-top           | 0        | Top value                                                 |
| --slide-background-end           |          | In LTR, right value                                       |
| --slide-background-start         | 0        | In LTR, left value                                        |
| --slide-background-width         |          | A background width, default without being set all width   |
| --slide-background-height        |          | A background height, default without being set all height |
| --slide-background-print-display | none     | Don't print per default the background                    |

## Examples

An example with an image cloned as background for each slides:

```
<deckgo-deck>
  <deckgo-slide-title>
    <h1 slot="title">My presentation title</h1>
    <p slot="content">
      Hello World 🚀
    </p>
  </deckgo-slide-title>

  <img slot="background" data-src="https://deckdeckgo.com/assets/favicon/android-chrome-512x512.png">
</deckgo-deck>
```

An example with a more complex html and css element which is set as background for the all presentation:

```
<deckgo-deck clone-background="false">
  <deckgo-slide-title>
    <h1 slot="title">My presentation title</h1>
    <p slot="content">
      Hello World 🚀
    </p>
  </deckgo-slide-title>

  <div class="circle" slot="background"></div>
</deckgo-deck>
```

where for example the related `circle` css code could be:

```
div.circle {
  position: absolute;
  left: 50%;
  transform: translate(-50%, 0);

  bottom: -10vh;
  width: 800vw;
  height: 100vh;

  border-radius: 50%;
  background: yellow;
  opacity: 0.3;
}
```

[deckdeckgo]: https://deckdeckgo.com
