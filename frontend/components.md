[Main](../readme.md)

# Angular Components

## Components

- File length:
    - Ideal: 0-300 lines
    - Max: 500 lines
- Logic
    - Both business and RESTful logic to be exported into services
- Naming
    - filename and component to be named identical


### Example:
my-component.component.ts
```typescript
/**
* Import should be in alphabetical order 
*/
import { Component, Input } from '@angular/core';
import { FormGroup } from '@angular/forms';
import { MyComponentDataService } from './shared/my-component-data.service';
import { MyComponentHighlightingService } from './shared/my-component-highlighting.service';
import { MyType } from './shared/my-type';

@Component({
    /**
     * Selector should be equivalent to component class name
     * and file name. Prefix such as 'app-' should be avoided unless
     * necessary.
    */
    selector: 'my-component',
    /**
     * Inline templates are to be avoided. File should
     * also be used for templating.
    */
    templateUrl: './my-component.html',
    /**
     * Note: '.scss' file should be imported, not '.css'
     */
    styleUrls: ['./my-component.scss']
})
/**
* Class name should reflect filename 'my-component.component.ts'.
*/
export class MyComponent {

    /**
     * Inputs and outputs should be marked as 'public'.
     */
    @Input()
    public title: string;
    
    /**
     * Template properties should be marked as 'public'.
     */
    public myForm: FormGroup;
    
    /**
     * Properties (public and private) are to be documented
     * @example
     *  this.myOtherProperty = true;
     * @public
     * @type {boolean}
     * @default false
     */
    public myOtherPublicProperty: boolean;
    
    /**
     * Properties with no explicit accessor is not allowed
     */
    myOtherProperty: number;
    
    /**
     * 'any' types are not permitted unless a 3rd party framework
     * explicitly uses it.
     * Even trivially inferred types should be declared such as boolean and string.
     */
    private body: MyType;

    /**
     * Business logic is to be extracted to service by functionality
     */
    constructor(private myComponentDataService: MyComponentDataService,
                private myComponentHighlightingService: MyComponentHighlightingService) {
    }

    /**
     * All public methods should be documented.
     * 
     * @param {string} $event text passed from the input
     */
    public onButtonClick($event: string): void {
        this.myComponentDataService.submitData(this.myForm);
    }

    /**
     * Private methods must not be documented unless complex
     * TODO: Complexity algorithm needed
     * 
     * @private
     * @returns {boolean} 
     */
    private somethingMoreComplex(): boolean {
        return true;
    }

}
```
