# Best practices for frontend development

CSS
- You should be able to understand what every single css rule does and why it has been written by looking at CSS alone. 
- To hide pseudo elements (:before, :after) use content: none; instead of display: none;
- Avoid using "!important". If you use it, add a  comment to explain why you had to use it.
- Avoid using negative margins and paddings. If you use them, add comment to explain why you had to use them.
- Before using new css rules, make sure you are aware of known issues in different browsers. These issues are listed on caniuse.com. For example "box-sizing: border-box;" can cause issues in Internet Explorer 9.
- All css rules for a module/component should be name spaced to avoid affecting elements outside the module/component.

JavaScript
- Do not trigger standard user interface events (click, scroll, ...) and instead invoke the handler set for those events. The are two reasons for this. One that there is no bullet-proof way to differentiate events triggered by user from those triggered by code, so if user actions are being tracked for analytics, triggering same event by code will produce wrong tracking data. Second reason is that chances are that handlers are set for these events by other scripts running in the same page which you don't want to invoke.

HTML
- Use data-camel-case rather than data-camelCase for data attribute names if the project uses jQuery. jQuery.data() chocks on camcelCase names of data attributes, hence breaking your code. https://jsfiddle.net/smohadjer/tua0v2x6/
