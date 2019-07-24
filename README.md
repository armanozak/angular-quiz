# Angular Technical Quiz

This repo is a collection of fill-in-the-blanks questions to test your Angular skills.

Due to the nature of the questions, some of them may feel unusually, even unnecessarily, difficult. Please do not feel uncomfortable. The ultimate goal of this quiz is to help people taking it refresh their memory, nothing else. Furthermore, the difficulty levels given are only a comparison between these questions and not noteworthy at all.

Good luck!

## Syntax/Domain Specific Language

### Question 1.1

![Low difficulty][low] 
Fill in the blanks in order and make the `<img>` element to display the `some-pic.jpg` and log the event fired the image is successfully loaded.

```ts
@Component({
  template: `
    <img                                           />
  `,
})
export class SomeComponent {

  src = '/assets/img/some-pic.jpg';

  log(context: any) {
    console.log(context);
  }

}
```

---

### Question 1.2

![Low difficulty][low] 
Fill in the blanks to display the value of `<input>` inside the `<div>` and make sure the text gets updated whenever the value changes.

```ts
@Component({
  template: `
    <input type="text"                              >

    <div>                </div>
  `,
})
export class SomeComponent {
  value = '';
}
```

---

### Question 1.3

![Low difficulty][low] 
Fill in the blanks to add a class called `active` to the `<div>` element when the value of `isActive` is `true`.

```html
<!-- some.component.html  -->

<div [                    ]="isActive">
  Placeholder text...
</div>
```

---

### Question 1.4

![Low difficulty][low] 
Fill in the blanks to set the height of the `<div>` element to **24 pixels** when the value of `currentHeight` is `24`.

```html
<!-- some.component.html  -->

<div [                    ]="currentHeight">
  Placeholder text...
</div>
```

---

### Question 1.5

![Low difficulty][low] 
Fill in the blanks to list each name in `people` and enumerate them starting from 1 (such as 1. John). Make sure you only use the given blank interpolation.

```ts
@Component({
  template: `
    <ul>
      <li *ngFor="let person of people                  ">
        {{                                     }}
      </li>
    </ul>
  `,
})
export class SomeComponent {
  people = [
    { id: 10001, name: 'John' },
    { id: 10002, name: 'Mary' },
    { id: 10003, name: 'Fred' },
    { id: 10003, name: 'Lisa' },
  ];
}
```

---

### Question 1.6

![Low difficulty][low] 
Fill in the blanks to display `Loading...` until data gets loaded.

```ts
@Component({
  template: `
    <div *ngIf="data$ | async as data                 ">
      {{ data }}
    </div>

    <                               >
      Loading...
    </                              >
  `,
})
export class SomeComponent {
  data$: Observable<string>;

  constructor(private someService: SomeService) {
    this.data$ = this.someService.getSomeRemoteDataOnce();
  }
}
```

---

### Question 1.7

![Medium difficulty][medium] 
Fill in the blanks to display `Hello World!` in **bold** on the screen. Make sure new text is displayed whenever `greting` of `ParentComponent` changes. 

```ts
@Component({
  selector: 'app-some',
  template: `
    <strong>

    </strong>
  `,
})
export class SomeComponent {}


@Component({
  selector: 'app-parent',
  template: `<app-some>{{ greeting }}</app-some>`,
})
export class ParentComponent {
  @Input()
  greeting = 'Hello World!';
}
```

---

### Question 1.8

![Medium difficulty][medium] 
Fill in the blanks to display `Hello World!` on the screen.

```ts
@Component({
  template: `
    <ng-container
      *ngTemplateOutlet="                                        "
    ></ng-container>
    
    <ng-template #greeting let-name>
      Hello {{name}}!
    </ng-template>
  `,
})
export class SomeComponent {
  context = {
    id: 1,
    name: 'World',
  };
}
```

---

### Question 1.9

![Medium difficulty][medium] 
Fill in the blanks to log `Hello World!` on every click on the `<button>`.

```ts
@Directive({
  selector: '[appSome]',
  exportAs: 'appSomeDir',
})
export class SomeDirective {
  greeting = 'Hello World!';
}


@Component({
  template: `
    <button
      appSome


      (click)="log(                      )"
    >
      GREET
    </button>
  `,
})
export class SomeComponent {

  log(message: string): void {
    console.log(message);
  }

}
```

---

### Question 1.10

![Low difficulty][low] 
Fill in the blanks to display `Hello World!` on the screen.

```ts
@Component({
  template: `<div [               ]="greeting"></div>`,
})
export class SomeComponent {
  greeting = 'Hello World!';
}
```

---

### Question 1.11

![Low difficulty][low] 
Fill in the blanks to add an `aria-label` to it.

```ts
@Component({
  template: `
    <button [                       ]="label">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16">
        <path fill="#000" d="M 2.59375 1 C 1.71875 1 1 1.71875 1 2.59375 L 1 12.40625 C 1 13.28125 1.71875 14 2.59375 14 L 12.40625 14 C 13.28125 14 14 13.28125 14 12.40625 L 14 4.042969 L 10.957031 1 Z M 2.59375 2 L 3 2 L 3 5 C 3 5.546875 3.453125 6 4 6 L 10 6 C 10.546875 6 11 5.546875 11 5 L 11 2.457031 L 13 4.457031 L 13 12.40625 C 13 12.742188 12.738281 13 12.40625 13 L 11 13 L 11 10 C 11 9.453125 10.546875 9 10 9 L 5 9 C 4.453125 9 4 9.453125 4 10 L 4 13 L 2.59375 13 C 2.257813 13 2 12.738281 2 12.40625 L 2 2.59375 C 2 2.257813 2.257813 2 2.59375 2 Z M 4 2 L 7 2 L 7 4 L 9 4 L 9 2 L 10 2 L 10 5 L 4 5 Z M 5 10 L 10 10 L 10 13 L 5 13 Z "></path>
      </svg>
    </button>
  `,
})
export class SomeComponent {

  @Input()
  label = 'Save as draft';

}
```

---

### Question 1.12

![Low difficulty][low] 
Fill in the blanks to display `Hello World!` on the screen.

```ts
@Component({
  template: `{= greeting =}`,



})
export class SomeComponent {
  greeting = 'Hello World!';
}
```

---

### Question 1.13

![Low difficulty][low] 
Fill in the blanks to display `<input>` value on the screen.

```ts
@Component({
  template: `
    <input                               >
    {{ someInput.value }}
  `,
})
export class SomeComponent {}
```

---

### Question 1.14

![Medium difficulty][medium] 
Fill in the blanks to make `<button>` disabled. Make sure it gets enabled again, when `isEnabled` is set to `true`.

```ts
@Component({
  template: `
    <button        disabled="              ">
      CLICK HERE
    </button>
  `,
})
export class SomeComponent {

  @Input()
  isEnabled = false;

}
```

---

### Question 1.15

![Medium difficulty][medium] 
Fill in the blanks to log the event fired when `<button>` is clicked.

```ts
@Component({
  template: `
    <button       click="log(             )">
      CLICK HERE
    </button>
  `,
})
export class SomeComponent {

  log(event: MouseEvent) {
    console.log(event);
  }

}
```

---

### Question 1.16

![High difficulty][high] 
Fill in the blanks to display `15` on the screen.

```ts
@Directive({
  selector: '[appMultiply]',
})
export class MultiplyDirective {

  @Input('appMultiplyBe')
  multiplicand: number;

  @Input('appMultiplyTimes')
  multiplier: number;

  constructor(
    private tempRef: TemplateRef<any>,
    private vcRef: ViewContainerRef,
  ) {}

  private clearProduct() {
    this.vcRef.clear();
  }

  private projectProduct() {
    this.vcRef.createEmbeddedView(
      this.tempRef,
      {
        $implicit: this.multiplicand * this.multiplier,
      },
    );
  }

  ngOnChanges() {
    this.clearProduct();
    this.projectProduct();
  }

}

@Component({
  template: `
    <div                                               >
      {{ product }}
    </div>
  `,
})
export class SomeComponent {

  n1 = 5;
  
  n2 = 3;

}
```

 

---

 

## API

### Question 2.1

![Low difficulty][low] 
Fill in the blanks to use `some.component.html` as template and `some.component.css` as style for this component. They are in the same folder as the TypeScript file.

```ts
@Component({
  selector: 'app-some',


  
})
export class SomeComponent {}
```

---

### Question 2.2

![Low difficulty][low] 
Fill in the blanks to avoid re-calculation of `name` unless `firstName` or `lastName` changes.

```ts
@Component({
  selector: 'app-some',
  template: `<div>{{ name }}</div>`,
  

})
export class SomeComponent {

  @Input()
  firstName = '';

  @Input()
  lastName = '';

  get name(): string {
    return `${this.firstName} ${this.lastName}`;
  }

}
```

---

### Question 2.3

![Low difficulty][low] 
Fill in the blanks to remove underlines from `<a>` elements inside the child component, i.e. `<app-child>`.

```ts
@Component({
  template: `<app-child></app-child>`,
  styles: [
    `
    app-child a {
      text-decoration: none;
    }
    `,
  ],
  

})
export class SomeComponent {}
```

---

### Question 2.4

![Low difficulty][low] 
Fill in the blanks to display `Hello World!` on the screen. Note that `SomeService` is not provided anywhere in the project.

```ts
@Injectable()
export class SomeService {
  getSomeProp(): string {
    return 'Hello World!';
  }
}


@Component({
  template: `{{ someProp }}`,




})
export class SomeComponent {

  get someProp(): string {
    return this.someService.getSomeProp();
  }





}
```

---

### Question 2.5

![Medium difficulty][medium] 
Fill in the blanks to log the latest status at every toggle of the `<input>`.

```ts
@Component({
  selector: 'app-some',
  template: `
    <label [               ]="uuid">
      <input
        [      ]="uuid"
        type="checkbox"



      >
      Status: {{ status }}
    </label>
  `,
})
export class SomeComponent {
  @Input()
  uuid = generateUUID();

  @Output()
  onToggle = new EventEmitter<boolean>();

  selected = false;

  onChange() {



  }
}


@Component({
  template: `<app-some                           "></app-some>`,
})
export class ParentComponent {

  log(status: boolean) {
    console.log(status);
  }

}
```

---

### Question 2.6

![Medium difficulty][medium] 
Fill in the blanks to make sure only the changed items are rendered and the unchanged items are preserved when the list of people changes.

```ts
@Component({
  selector: 'app-some',
  template: `
    <ul>
      <li *ngFor="let person of people                         ">
        {{ person.name }}
      </li>
    </ul>
  `,
})
export class SomeComponent {

  @Input()
  people = [
    { id: 10001, name: 'John' },
    { id: 10002, name: 'Mary' },
    { id: 10003, name: 'Fred' },
    { id: 10003, name: 'Lisa' },
  ];




}
```

---

### Question 2.7

![Medium difficulty][medium] 
Fill in the blanks to obtain a directive that adds `target="_blank"` as attribute to all `<a>` elements which are not a `routerLink`. 

```ts
@Directive({
  selector: '                          ',
})
export class ExternalLinkDirective {





}
```

---

### Question 2.8

![Medium difficulty][medium] 
Fill in the blanks to display `Hello World!` on the screen.

```ts
@Component({
  selector: 'app-child',
  template: `{{ greeting }}`,
})
export class ChildComponent {
  constructor(
    

    public greeting: string,
  ) {}
}

@Component({
  selector: 'app-some',
  template: `<ng-content></ng-content>`,







})
export class SomeComponent {}


@Component({
  selector: 'app-parent',
  template: `<app-some><app-child></app-child></app-some>`,
})
export class ParentComponent {}
```

---

### Question 2.9

![Medium difficulty][medium] 
Fill in the blanks to display `Hello World!` on the screen.

```ts
@Directive({
  selector: '[appSome]',
})
export class SomeDirective {



  greeting = 'Hello World!';

}


@Component({
  template: `<div appSome></div>`,
})
export class SomeComponent {}
```

---

### Question 2.10

![Medium difficulty][medium] 
Fill in the blanks to **securely** display the html content on the screen. Note that empty string is just a default value and `content` might be set to any string.

```ts
@Component({
  template: `<div [innerHTML]="html"></div>`,
})
export class SomeComponent {
  @Input()
  content = '';

  get html():         {



  }




}
```







[low]: https://img.shields.io/badge/-LOW-1CAC78.svg "Low difficulty"
[medium]: https://img.shields.io/badge/-MEDIUM-FB9902.svg "Medium difficulty"
[high]: https://img.shields.io/badge/-HIGH-FF4040.svg "High difficulty"
