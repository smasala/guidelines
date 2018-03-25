[Main](../readme.md)

# Styling

- All styling should take place in `.scss` (sass) files

## Example

```scss
@import "../styles/colours";

:host {
    // host styles
}

:host-context(.isOpen) {
    // do something when the host context meets a rule
}

::ng-deep {
    // I'm using a 3rd party framework which I need to manipulate
    // NOT own sub components
}

.my-box {
    // first own css properties
    // colours and similar variables should be delcared globally
    background-color: map-get($material-colours, black);
    // followed by pseudo classes and other 'parent (&)' selectors. 
    &:hover {
        // something
    }
    // followed by child classes
    .my-child {
        text-align: :center;
        // something
        &:hover {
            // -
        }
        &.open {
            // -
        }
        .more {
            // -
        }
    }
}
```