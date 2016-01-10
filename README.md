#Front-end Tips

##CSS
- Comment CSS rules (or collection of rules) that their purpose is not obvious.
- Use "content: none" to hide pseudo elements (:before, :after) rather than "display: none".
- Avoid "!important". If you have to use it, add a  comment to explain why.
- Avoid negative margins. If you have to use them, add comment to explain why.
- If you are using a css property for the first time, make sure you are aware of known issues in browsers you support (these issues are listed on caniuse.com). For example "box-sizing: border-box;" can cause issues in Internet Explorer 9.
- All css rules for a module/component should be name spaced to avoid affecting elements outside that module/component.

##JavaScript
- Do not trigger standard user interface events (click, scroll, ...) and instead invoke the handler set for those events. There are two reasons for this. One that there is no bullet-proof way to differentiate events triggered by user from those triggered by code, so if user actions are being tracked for analytics, triggering same event by code will produce false positive results. Second reason is that chances are handlers are set for the same event by other scripts running in the same page which you don't want to invoke.

##HTML
- Use data-camel-case rather than data-camelCase to name data attributes if the project uses jQuery. jQuery.data() chocks when parsing data-camcelCase attributes, hence breaking your code (e.g. https://jsfiddle.net/smohadjer/tua0v2x6/4/).
