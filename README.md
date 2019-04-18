# animate.css
pure css animations by leon zündel

you can choose between:

* viewport animations
* hover animations 
* attraction animations
* loading animations

[view demo here](https://raw.githack.com/leonzuendel/animate.css/master/demo.html)

## getting started

1. download the file/s and move the animate.css into your project folder
2. link the animate.css to your html document with `<link rel="stylesheet" href="animate.css">`
3. have a look at the demo.html (or the link above) and add the name of the animation as a class to your element/s or copy the html code (for loading animations) into your html document
4. let the animate.css do all the magic

**attraction animations need to get the following css code to play: `animation-playstate: running` and `animation-iteration-count: infinite;` to replay infinitely**

**for the viewport animations you also need [jQuery](https://jquery.com) (`<script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>`) and this codesnippet in your functions.js or inside `<script>` `</script>` tags:**
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
