# animate.css
pure css animations by leon zündel

you can choose between:

* viewport animations
* hover animations 
* attraction animations

[view demo here](https://raw.githack.com/leonzuendel/animate.css/master/demo.html)

## getting started

1. download the file/s and move the animate.css into your project folder
2. link the animate.css to your html document with `<link rel="stylesheet" href="animate.css">`
3. have a look at the demo.html (or the link above) and add the name of the animation as a class to your element/s
4. let the animate.css do all the magic

**for the viewport animations you also need to add this codesnippet to your functions.js or into `<script>` tags:**
```
jQuery(document).ready(function ($) {
    function checkViewportAnimations() {
        $(".animate").each(function (index, element) {
            if(isElementOutViewport(element)){
                return;
            }
            $(this).addClass('active');
        });
    }

    checkViewportAnimations();

    $(window).scroll(function () {
        checkViewportAnimations();
    });
});

window.isElementOutViewport = function (el) {
    if(el == null){
        return false;
    }
    var rect = el.getBoundingClientRect();
    return rect.bottom < 0 || rect.right < 0 || rect.left > window.innerWidth || rect.top > window.innerHeight;
};
```
