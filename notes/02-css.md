# CSS
Padding = inside border
Margin = outside border used for spacing between other elements

em is sized based off of text size of the element.

For border raduis on button percentage makes oval use em

To make variables in css use
:root{
 --myColor: color;
 --otherColor: color;
}
To use variable use var(--myColor)
Body has margin by default in html
Margin: 0;

lecture - animations/styling

container fluid in templates
style: overflow hidden on parent div will get rid of overfloww - last resort

css                                     v happens once. infinite is continuous
animation: fadeIn 2s ease-in-out 2s forwards
opacity: 0 - starts invis         ^how long til it starts


@keyframes fadeIn{
    0%{     - 0%at start
        opactiy: 0;
    }
    100%{
        opacity: 1;   - stays at this opacity after the 2s.
        pointer-events: none; - wont be clickable
    }
}

fadeOut would be the opposite

transform: translateX(-100%) - moves the property to the left by 100%, off the page
                        (0%) - orignal position
use overflow-X hidden on parent so no side scroll on the row.

pseudo class selectors ::before and ::after
inserts content before/after element 
content: ''; text before/after elem
top: 5em;
right: 0%;
width: 100% - of the element
height: 100% - of the element

transform: perspective(1em) rotateX(40deg) scale(1, .35)- perspective first

animatebackgrounds.me free animated background
see some cool stuff on other websites yoink with the elem selector

scrolling image use repeat with big img - super high def img.
background-position in keyframes to move around image

even keyframes for smoother animations

60, 120sec good for background effects, too fast is too distracting from main content

alternate on animation goes from 100 to 0 if infinite 0-100-0-100

dont be afraid to break stuff when animating can learn cool stuff.

color psychology
    right amount of color for urgency
    60-30-10
