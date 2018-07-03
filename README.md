# ng-phone-mask

## Installation

To install this library, run:

```bash
$ npm install ng-phone-mask --save
```

## Consuming your library

Once you have installed it you can import `InternationalPhoneNumberModule` from `ngx-international-phone-number` in any application module. E.g.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { InternationalPhoneNumberModule } from 'ng-phone-mask';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // InternationalPhoneNumberModule module
    InternationalPhoneNumberModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once it is imported, you can use `international-phone-number`:

```xml
<!-- app.component.html -->
<form name="sample-form" (ngSubmit)="submit()" #f="ngForm">
 <international-phone-number [(ngModel)]="model.phone_number" placeholder="Enter phone number" [maxlength]="20" [defaultCountry]="'in'" [required]="true" #phone_number="ngModel" name="phone_number"></international-phone-number>

  <div *ngIf="f.submitted && !phone_number.valid" class="help-block">Phone number is required and should be valid</div>
  <button type="submit">Submit</button>
</form>
```

### Attributes/Options:
       defaultCountryCode : An ISO 639-1 country code can be provided to set default country selected.
       placeholder: A placeholder text which would be displayed in input widget
       required: Indicates whether it's required or not
       allowDropdown: Indicates whether to allow selecting country from dropdown


## Troubleshooting:
If you are getting error "Can't resolve 'google-libphonenumber'" while building with aot, try to install google-libphonenumber. Run npm install google-libphonenumber@3.0.9 --save


## Authors
    * Original Author: kondi0, nikhiln
    * Author: Jarvis 
## License

MIT
