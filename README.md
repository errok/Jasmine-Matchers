# Jasmine-Matchers [![](https://travis-ci.org/JamieMason/Jasmine-Matchers.svg?branch=develop)](https://travis-ci.org/JamieMason/Jasmine-Matchers)

> Simple, clear, helpful, readable tests.

The [Jasmine testing framework](http://pivotal.github.com/jasmine/) from [Pivotal Labs](http://pivotallabs.com/) comes with this [default set of matchers](https://github.com/pivotal/jasmine/wiki/Matchers);

```javascript
expect(fn).toThrow(e);
expect(instance).toBe(instance);
expect(mixed).toBeDefined();
expect(mixed).toBeFalsy();
expect(number).toBeGreaterThan(number);
expect(number).toBeLessThan(number);
expect(mixed).toBeNull();
expect(mixed).toBeTruthy();
expect(mixed).toBeUndefined();
expect(array).toContain(member);
expect(string).toContain(substring);
expect(mixed).toEqual(mixed);
expect(mixed).toMatch(pattern);
```

Using the default Matchers your tests and failure output might look something like this;

```javascript
it('should expose the expected API', function() {
  expect(typeof record.save).toEqual('function');
});
```

> Expected "undefined" to equal "function"

```javascript
it('should distribute evenly', function() {
  expect(basket.items % 2 === 0).toEqual(true);
});
```

> Expected false to equal true

Using [Jasmine-Matchers](https://github.com/JamieMason/Jasmine-Matchers) the same tests and failure output can be written like this;

```javascript
it('should expose the expected API', function() {
  expect(record).toHaveMethod('save');
});
```

> Expected member "save" of { save : Function } to be function.

```javascript
it('should distribute evenly', function() {
  expect(person).toHaveEvenNumber('age');
});
```

> Expected member "age" of { name : 'Guybrush', age : 25 } to be even number.

## Installation

### npm

```bash
npm install jasmine-expect --save-dev
```

### Bower

```bash
bower install jasmine-expect --save-dev
```

### Manual

Download [https://github.com/JamieMason/Jasmine-Matchers/archive/1.52.0.zip]()

## Integration

### Browser

Include Jasmine Matchers after Jasmine but before your tests.

```html
<script src="/path/to/jasmine-matchers.js"></script>
```

### Karma

Integration is easy with the [karma-jasmine-matchers](https://github.com/JamieMason/karma-jasmine-matchers) plugin.

### Sublime Text

[Jasmine-Matchers-Snippets](https://github.com/JamieMason/Jasmine-Matchers-Snippets) can be installed with [Package Control](https://packagecontrol.io/packages/Jasmine%20Matchers%20Snippets) to ease development with Jasmine Matchers in Sublime Text.

## Available Matchers

### Arrays

```javascript
expect(array).toBeArray();
expect(array).toBeArrayOfBooleans();
expect(array).toBeArrayOfNumbers();
expect(array).toBeArrayOfObjects();
expect(array).toBeArrayOfSize(size);
expect(array).toBeArrayOfStrings();
expect(array).toBeEmptyArray();
expect(array).toBeNonEmptyArray();
expect(object).toHaveArray(memberName);
expect(object).toHaveArrayOfBooleans(memberName);
expect(object).toHaveArrayOfNumbers(memberName);
expect(object).toHaveArrayOfObjects(memberName);
expect(object).toHaveArrayOfSize(memberName, size);
expect(object).toHaveArrayOfStrings(memberName);
expect(object).toHaveEmptyArray(memberName);
expect(object).toHaveNonEmptyArray(memberName);
```

### Booleans

```javascript
expect(boolean).toBeBoolean();
expect(boolean).toBeFalse();
expect(boolean).toBeTrue();
expect(object).toHaveBoolean(memberName);
expect(object).toHaveFalse(memberName);
expect(object).toHaveTrue(memberName);
```

### Browser

```javascript
expect(document).toBeDocument();
expect(htmlElement).toBeHtmlCommentNode();
expect(htmlElement).toBeHtmlNode();
expect(htmlElement).toBeHtmlTextNode();
expect(object).toHaveHtmlNode(memberName);
expect(window).toBeWindow();
```

### Dates

```javascript
expect(date).toBeAfter(date);
expect(date).toBeBefore(date);
expect(date).toBeDate();
expect(string).toBeIso8601();
expect(object).toHaveDate(memberName);
expect(object).toHaveDateAfter(memberName, date);
expect(object).toHaveDateBefore(memberName, date);
expect(object).toHaveIso8601(memberName);
```

### Functions and Errors

```javascript
expect(function).toBeFunction();
expect(function).toThrowError();
expect(function).toThrowErrorOfType(type);
expect(object).toHaveMethod(memberName);
```

### Numbers

```javascript
expect(mixed).toBeCalculable();
expect(number).toBeEvenNumber();
expect(number).toBeNumber();
expect(number).toBeOddNumber();
expect(number).toBeWholeNumber();
expect(number).toBeWithinRange(floor, ceiling);
expect(object).toHaveCalculable(memberName);
expect(object).toHaveEvenNumber(memberName);
expect(object).toHaveNumber(memberName);
expect(object).toHaveNumberWithinRange(memberName, floor, ceiling);
expect(object).toHaveOddNumber(memberName);
expect(object).toHaveWholeNumber(memberName);
```

### Objects

```javascript
expect(object).toBeEmptyObject();
expect(object).toBeNonEmptyObject();
expect(object).toBeObject();
expect(object).toHaveEmptyObject(memberName);
expect(object).toHaveMember(memberName);
expect(object).toHaveNonEmptyObject(memberName);
expect(object).toHaveObject(memberName);
expect(object).toImplement(other);
```

### Strings

```javascript
expect(string).toBeEmptyString();
expect(string).toBeHtmlString();
expect(string).toBeJsonString();
expect(string).toBeLongerThan(other);
expect(string).toBeNonEmptyString();
expect(string).toBeSameLengthAs(other);
expect(string).toBeShorterThan(other);
expect(string).toBeString();
expect(string).toBeWhitespace();
expect(string).toEndWith(expected);
expect(string).toStartWith(expected);
expect(object).toHaveEmptyString(memberName);
expect(object).toHaveHtmlString(memberName);
expect(object).toHaveJsonString(memberName);
expect(object).toHaveNonEmptyString(memberName);
expect(object).toHaveString(memberName);
expect(object).toHaveStringLongerThan(memberName, other);
expect(object).toHaveStringSameLengthAs(memberName, other);
expect(object).toHaveStringShorterThan(memberName, other);
expect(object).toHaveWhitespaceString(memberName);
```
