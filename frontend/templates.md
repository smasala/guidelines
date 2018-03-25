[Main](../readme.md)

# Templates

- Complex or separate functionality should be extract into sub components
- Inline styles should be avoided and css classes used instead
- Events should call public functions by identifiable names.
- Templates should be written and maintained in `html` files
    - Tip: `vscode` provides support for missing property declarations in templates and finding references (`ctrl + click`)

## Example

my-component.html

```html
<h1>
    {{ title }}
</h1>
    <my-second-component
        style="display: block;"
        [class.myClass]="showMe"
        (click)="onDeleteClick($event)"
        [items]="listItems">
    </my-second-component>
<button class="btn" [class.btn-primary]="isActive">
    Click me
</button>
```