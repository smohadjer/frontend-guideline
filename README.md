# Best practices for frontend development

CSS
- Avoid selectors that are too generic as they could have undesired effects. 
- You should be able to udnerstand what every single rule does and why it has been written by looking at CSS alone. 
- Do not use universal selector. It's too risky.
- To hide pseudo elements (:before, :after) use content: none; instead of display: none;
- Avoid using "!important". If you use it, add a  comment to explain why you had to use it.
- Avoid using negative margins and paddings. If you use them, add comment to explain why you had to use it.
- Before using new css rules, make sure you are aware of known issues in different browsers. These are listed on caniuse.com. For example box-sizing: border-box can cause issues in ie8/ie9.
- All css rules for a module should be name spaced to avoid affecting elements outside the module.

JavaScript
- Do not trigger UI events (click, scroll, etc) by script and instead call their event handler. There is no bullet-proof way to differentiate events triggered by user from those triggered by code, so if user actions are being tracked for analytics, triggering same event by code will result in false positive results. Also chances are there are handlers set in other code run in the same page for the event and you will unintentionally trigger those handlers. 
