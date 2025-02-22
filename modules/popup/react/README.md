# Canvas Kit Popup

A Popup component that allows you to render content above another.

Note: This popup does not include a positioning engined. In our example we use Material UIs popper
component to wrap our Popup component and position it, which is a wrapper to Popper.js. For
reference: https://material-ui.com/api/popper/

## Installation

```sh
yarn add @workday/canvas-kit-react
```

or

```sh
yarn add @workday/canvas-kit-react-popup
```

## Usage

```tsx
import * as React from 'react';
import Popper from '@material-ui/core/Popper';
import {Popup} from '@workday/canvas-kit-react-popup';

// We use Popper from Material UI for our positioning
<Popper placement={'bottom'} open={this.state.open} anchorEl={anchorEl}>
  <Popup
    width={300}
    heading={'Popup Title'}
    padding={Popup.Padding.l}
    handleClose={this.handleClose}
  >
    {this.props.children}
  </Popup>
</Popper>;
```

## Static Properties

#### `Padding: PopupPadding`

```tsx
<Popup padding={Popup.Padding.l}>{this.props.children}</Popup>
```

## Component Props

### Required

> None

---

### Optional

### `padding: PopupPadding`

> You can choose between zero, s, l for your padding

Default: `PopupPadding.l`

| Name   | Size (px) |
| ------ | --------- |
| `zero` | 0         |
| `s`    | 16        |
| `l`    | 32        |

#### `handleClose: () => void`

> Callback to handle close of your Popup and any other event when the Popup is closed.

---

#### `width: number | string`

> Width of the card.

---

#### `depth: CanvasDepthValue`

> Depth of the card. Style imported from `@workday/canvas-kit-react-core`.

Default: `depth[2]`

---

#### `transformOrigin: TransformOrigin`

> Origin from which the popup will animate from

Default:

```js
{
  horizontal: 'center',
  vertical: 'top',
}
```

---

#### `heading: ReactNode`

> Heading at the top of the card.

---

#### `closeIconSize: ButtonSizes`

> The size of the close icon button (small or medium)

---

#### `popupRef: React.Ref<HTMLDivElement>`

> A ref to the underlying popup container element. Use this to check click targets against when
> closing a popup.
