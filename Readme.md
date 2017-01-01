This code snippet explains how ng-content works

ng-content is mainly used to insert the template data from host comonent to child component

For Ex:

In Host Component,say app_component.ts
we have custom tags
<zippy>
  This is my zippy
</zippy>

and this needs to be inserted into your child component zippy_component.ts

@Component({
    selector: 'zippy'
    template: `
    <div class="zippy">
        <div
            class="zippy-title"
            (click)="toggle()">
            {{ title }}
            <i>
                class="pull-right glyphicon"
                [ngClass]="
                    {
                        'glyphicon-chevron-down': !isExpanded,
                        'glyphicon-chevron-up': isExpanded
                    }"
            </i>
        </div>
        <div *ngIf="isExpanded" class="zippy-content">
            <ng-content></ng-content>
        </div>
    </div>
    `
...
)}

You can see the ng-content tag, which refers the selector zippy, and finds the correspnding tag in host component and replaces the tamplate data.

This can also be done by using @Input , but that clutters your code, and it is good to use ng-content whenever there is a loarge snippet of code needs to be inserted.


Thank You.

Please wait for my detailed blog on ng-content, viewchildren and viewcontentchildren

