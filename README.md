# Front-end Tips

## CSS
- Comment CSS rules (or collection of rules) that their purpose is not obvious.
- Use "content: none" to hide pseudo elements (:before, :after) rather than "display: none".
- Avoid "!important". If you have to use it, add a  comment to explain why.
- Avoid negative margins. If you have to use them, add comment to explain why.
- If you are using a css property for the first time, make sure you are aware of known issues in browsers you support (these issues are listed on caniuse.com). For example "box-sizing: border-box;" can cause issues in Internet Explorer 9.
- All css rules for a module/component should be name spaced to avoid affecting elements outside that module/component.
- To target the first x children of an element, use :nth-child(-n + x).
- To remove hover underline from a:before set a:before's display to [inline-block](http://stackoverflow.com/questions/8820286/how-to-remove-only-underline-from-abefore). 


## JavaScript/jQuery
- If you use a jQuery plugin or any script that you have not written yourself in a project, you carry resonsibility for any issues/bugs that the external code brings into the project, so choose causiously, and test code in prototypes before integrating into the project. Make sure project is active on gitHub and doesn't have open issues that affect your project.
- Do not trigger standard user interface events (click, scroll, ...) and instead invoke the handler set for those events. There are two reasons for this. One that there is no bullet-proof way to differentiate events triggered by user from those triggered by code, so if user actions are being tracked for analytics, triggering same event by code will produce false positive results. Second reason is that chances are handlers are set for the same event by other scripts running in the same page which you don't want to invoke.
- To simulate a user click on an anchor element in jquery use $(mylink)[0].click(). $(mylink).trigger('click'); only invokes myLink's click handler (if one is set via js) and won't simulate default behavior an anchor when user clicks it.
- To figure out if an element is displayed or not in jquery use $('element:visible') or $('element:hidden'). These selectors take display state of element's ancestors into account so if element itself is visible, but its parent not, $('element:visible') will return false.
- Don't attach handlers to the window scroll event and instead use a timer (setInterval). For why read this: http://ejohn.org/blog/learning-from-twitter/

## HTML
- Use data-camel-case rather than data-camelCase to name data attributes if the project uses jQuery. jQuery.data() chocks when parsing data-camcelCase attributes, hence breaking your code ([see jsfiddle] (https://jsfiddle.net/smohadjer/tua0v2x6/4/)).

## Working on a project
- Do not delete a file and then add it to another folder in order to achieve move or do not rename folders. Use `git mv <old name> <new name>` command instead so git history is preserved.
- Use [semver versioning](https://semver.org/) to release patches, minor, and major revisions. Patches and minor releases should be backward compatible.
- Add CHANGELOG.md to all repositories http://keepachangelog.com/en/1.0.0/

## Git
- To move multiple files to a folder you can use something like this: `git mv *.html mydestinationfolder/`
- To rename extension of multiple files: `for i in *.php; do git mv "$i" "${i/.php}".html; done`
