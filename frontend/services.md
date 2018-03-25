[Main](../readme.md)

# Services

- Contain RESTful or business logic
- Shared services which do not belong to a component should be located within a `'shared' module`
- Services can inject other services via the constructor

## Example:

```typescript
import { Injectable } from '@angular/core';
import { Response } from '@angular/http';
import { Observable } from 'rxjs/Observable';
import { MyHttpService } from '../../shared-module/my-http.service';
import { Item } from './item';

/**
 * This service gets some special date from the DB
 */
@Injectable()
export class MyComponentDataService {

    constructor(private myHttpService: MyHttpService) {
    }

    /**
     * Some function that gets data
     * 
     * @param {string} id DB id
     * @returns {Items[]} returns an array of all the items
     */
    public getDataForComponent(id: string): Observable<Item[]> {
        const newId: string = this.parseId(id);
        return this.doSomethingFirst(newId);
    }

    private doSomethingFirst(id: string): Observable<Item[]> {
        // do something
        return this.myHttpService.getById(id);
    }

    /**
     * This function is really complex so I better
     * write a comment about it.
     * 
     * @private
     * @param {string} id the id to be parsed
     * @returns {string} parsed Id ready for the DB
     */
    private parseId(id: string): string {
        return `db-key-${id}`;
    }

}

```