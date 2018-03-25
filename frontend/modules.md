[Main](../readme.md)

# Angular Modules

- Each component should be module
    - Rationale: https://stackoverflow.com/questions/49286448/

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