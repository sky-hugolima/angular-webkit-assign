# angular-webkit-assign
Angular JS framework patched with https://www.npmjs.com/package/webkit-assign

The webkit-assign patch is related to the following issues affecting some versions of webkit in iOS:
- https://github.com/angular/angular.js/issues/9128
- https://bugs.webkit.org/show_bug.cgi?id=138038

From my understanding the error that occurs in the Angular code seems to be related to it's code using the following syntax:

var someObj = Object.create(Object.prototype);
someObj.$$someAttr = someValue;

where someObj is created by Object.create, and the JIT in webkit (iOS 8), randomly generates an object with readonly properties.
