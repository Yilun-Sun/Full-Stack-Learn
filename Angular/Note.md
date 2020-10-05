<p dir='rtl' align='right'><a href="https://github.com/Yilun-Sun/Full-Stack-Learn/blob/master/README.md"> README.md➡</a></p>

# Angular

## Difference and comparison between ng-if and ng-show / ng-hide

- <kbd>ng-if</kbd> will remove elements from DOM. This means that all your handlers or anything else attached to those elements will be lost. For example, if you bound a click handler to one of child elements, when <kbd>ng-if</kbd> evaluates to false, that element will be removed from DOM and your click handler will not work any more, even after <kbd>ng-if</kbd> later evaluates to true and displays the element. You will need to reattach the handler.

- <kbd>ng-show/ng-hide</kbd> does not remove the elements from DOM. It uses CSS styles to hide/show elements (note: you might need to add your own classes). This way your handlers that were attached to children will not be lost.

- <kbd>ng-if</kbd> creates a child scope while <kbd>ng-show/ng-hide</kbd> does not

Elements that are not in the DOM have less performance impact and your web app might appear to be faster when using <kbd>ng-if</kbd> compared to <kbd>ng-show/ng-hide</kbd>. In my experience, the difference is negligible. Animations are possible when using both <kbd>ng-show/ng-hide</kbd> and <kbd>ng-if</kbd>, with examples for both in the Angular documentation.

<a href="https://stackoverflow.com/questions/21869283/when-to-favor-ng-if-vs-ng-show-ng-hide">Original link</a>
