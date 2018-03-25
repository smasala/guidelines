[Main](../readme.md)

# Angular Modules

- Each component should be isolated into a module
    - Rationale: https://stackoverflow.com/questions/49286448/
    - Tip: Angular component generator extension for `vscode` does this out-of-the-box

```
my-component (folder)
- my-component.module.ts
- my-component.component.ts
- my-component.scss
- my-component.html
- my-component.spec.ts
- shared (folder)
 - services / pipes / directives / interfaces
- child-components
 - ...
```