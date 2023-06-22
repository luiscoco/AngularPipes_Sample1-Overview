# pipes

https://angular.io/guide/pipes-overview

https://stackblitz.com/~/github.com/luiscoco/AngularTemplate_Sample8-PipesOverview

In Angular, "pipes" are a feature that allows you to transform and format data before displaying it in the template. Pipes are used to apply functions or filters to the data in an easy and concise way. They are represented by the "|" symbol and can be added to the interpolation expressions or binding statements in Angular templates.

## Sample 1
Here's a simple example to demonstrate the usage of pipes in Angular:

Let's say we have a component with a property called "name" which holds a string value. We want to display this name in uppercase format in the template. We can achieve this using the "uppercase" pipe. Here's how it would look:

Component:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>{{ name | uppercase }}</p>'
})
export class ExampleComponent {
  name = 'John Doe';
}
```

In the template, we use the pipe symbol (|) after the property "name" and specify the pipe we want to use, which in this case is "uppercase". The "uppercase" pipe will transform the value of "name" to uppercase before displaying it in the template.

Output:
JOHN DOE

## Sample 2
Here's another example where we want to format a date using the "date" pipe:

Component:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>{{ currentDate | date }}</p>'
})
export class ExampleComponent {
  currentDate = new Date();
}
```

In this case, the "date" pipe is used to format the "currentDate" property. The pipe takes care of converting the date object into a readable format based on the locale settings of your application.

Output (assuming the current date is June 11, 2023):
Jun 11, 2023

These are just a couple of simple examples to demonstrate the usage of pipes in Angular. There are various built-in pipes available in Angular, such as "uppercase", "lowercase", "date", "currency", "decimal", and more. You can also create your own custom pipes to suit your specific needs by implementing the PipeTransform interface.

Here's a list of some commonly used built-in pipes in Angular along with a brief description of each:

## DatePipe: 
Formats a date value according to the locale rules. 

```typescript
<p>{{ currentDate | date }}</p>
```

This example formats the currentDate property using the date pipe, which transforms the date value into a readable format based on the locale settings.

## DecimalPipe: 
Transforms a decimal number into a string representation using decimal notation.

```typescript
<p>{{ price | number:'1.2-2' }}</p>
```

Here, the price property is transformed into a string representation using decimal notation. The number pipe is used with a formatting pattern of '1.2-2', which specifies a minimum of one integer digit, two fraction digits, and a maximum of two fraction digits.

## PercentPipe: 
Transforms a decimal number into a percentage string representation.

```typescript
<p>{{ discount | percent }}</p>
```

In this example, the discount property is converted into a percentage string representation using the percent pipe.

## CurrencyPipe: 
Transforms a number into a currency string representation based on the current locale.

```typescript
<p>{{ totalAmount | currency:'USD':'symbol' }}</p>
```

The totalAmount property is transformed into a currency string representation using the currency pipe. The second parameter 'USD' specifies the currency code, and the third parameter 'symbol' indicates that the currency symbol should be displayed.

## JsonPipe: 
Converts an object into a JSON string representation.

```typescript
<p>{{ myObject | json }}</p>
```

Here, the myObject property, which is an object, is transformed into a JSON string representation using the json pipe.

## UpperCasePipe: 
Transforms a string to all uppercase characters.

```typescript
<p>{{ text | uppercase }}</p>
```

The text property is converted to all uppercase characters using the uppercase pipe.

## LowerCasePipe: 
Transforms a string to all lowercase characters.

```typescript
<p>{{ text | lowercase }}</p>p>
```

This example transforms the text property into all lowercase characters using the lowercase pipe.

## SlicePipe: 
Creates a new array or string by selecting a subset of an existing array or string.

```typescript
<p>{{ text | slice:0:10 }}</p>
```

Here, the slice pipe is used to create a new string containing the first 10 characters of the text property.

## AsyncPipe: 
Subscribes to an Observable or Promise and returns the latest value emitted by it.

```typescript
<p>{{ data$ | async }}</p>
```

Assuming data$ is an Observable, the async pipe is used to subscribe to it and display the latest emitted value.

## KeyValuePipe: 
Transforms an object or map into an array of key-value pairs.

```typescript
<div *ngFor="let item of myObject | keyvalue">
  <p>{{ item.key }}: {{ item.value }}</p>
</div>
```

This example uses the keyvalue pipe to iterate over the properties of the myObject object and display each key-value pair.

## I18nPluralPipe: 
Displays a value based on the pluralization rules of a given locale.

```typescript
<p>{{ itemCount }} {{ itemCount | i18nPlural: { '=0': 'No items', '=1': 'One item', 'other': '# items' } }}</p>
```

The i18nPlural pipe displays a value based on the pluralization rules. In this example, the itemCount property is used to display a message based on the number of items.

## I18nSelectPipe: 
Displays a value based on a mapping object and a given key.
These are just a few examples of the built-in pipes available in Angular. Each pipe has its own specific purpose and usage. You can find more information on these pipes and other advanced topics in the Angular documentation.

```typescript
<p>{{ gender | i18nSelect: { 'male': 'He', 'female': 'She', 'other': 'They' } }}</p>
```

The i18nSelect pipe displays a value based on a mapping object and a given key. Here, the gender property is used to determine the appropriate pronoun to display.

It's important to note that the availability of certain pipes may depend on the Angular version you are using. Additionally, Angular allows you to create your own custom pipes to handle specific transformations that may not be covered by the built-in pipes.




