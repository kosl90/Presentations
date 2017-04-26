# Animation

动画的两个含义：
一、动画本身，某种效果，包含了 CSS animation 以及 CSS transition。
二、 特指 CSS animation


## Animated properties

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties


## CSS & JavaScript

requestAnimationFrame


## transition

transition
transition-property none/all/property
transition-duration `<time>` 1s, 3ms
transition-delay `<time>`
transition-timing-function ease/ease-in/ease-out/ease-in-out/linear/step-start/step-end/steps(n, [end|start]?)/cubic-bezier(a, b, c, d)

https://developer.mozilla.org/en-US/docs/Web/CSS/single-transition-timing-function


## animation & keyframes

animation
animation-name none|<keyframes-name>
animation-duration
animation-timing-function
animation-delay
animation-iteration-count infinite/+<number> (float is ok)
animation-fill-mode none/forwards/backwards/both
animation-direction normal/reverse/alternate/alternate-reverse
animation-play-state running|paused

@keyframes


## events

animationstart
animationend
animationiteration
animationcancel

transitionstart
transitionend
transitionrun
transitioncancel

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions


## timing function

https://developer.mozilla.org/en-US/docs/Web/CSS/single-transition-timing-function


## transform

transform-style flat/preserve-3d 是否 3d 效果
translate/scale/rotate/skew/matrix/prespective

https://developer.mozilla.org/en-US/docs/Web/CSS/transform


## Browser Render

layout -> paint -> compose

https://developers.google.cn/web/fundamentals/performance/rendering/?hl=zh-cn


## FLIP

First
Last
Invert
Play


## DevTools

animation、paint


## Resources

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties

https://developer.mozilla.org/en-US/docs/Web/CSS/single-transition-timing-function

https://developer.mozilla.org/en-US/docs/Web/CSS/transform

https://csstriggers.com/

http://easings.net/zh-cn#

http://desandro.github.io/3dtransforms/
https://drafts.csswg.org/css-transforms-2/#perspective


https://developers.google.cn/web/fundamentals/performance/rendering/?hl=zh-cn