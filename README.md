# Flip_Card_SimpleWay
Simple way To Flip a Card
Always remember these steps for any flipping animation:  https://simplifiedweb.github.io/Flip_Card_SimpleWay/

Perspective should always be set on the parent container, and its value should be a minimum of 1000px for a depth effect.
Apply transform-style: preserve-3d to the card wrapper that contains all the elements to be flipped, such as two cards.
This is relevant to the flipping rotation.
Set backface-visibility: hidden: This property is essential when both sides of the card are present, and we wish to show only the front side. 
It hides the backside contents, revealing them only during the card flip.
Note that whichever element receives the transform-style property is responsible for rotating the front side when hovered. 
Apply rotateY(180deg) to it. For the back side, apply rotateY(180deg) to achieve rotation.

Why don't we apply the hover effect to both the front and back sides? 
Why do we only apply the hover effect to the container that wraps both the cards and not to the individual front and back sides? 
Why apply the rotation property only to the back side?

These are all valid questions. The reason is that when we hover over the front side to trigger a flip, 
we would expect the back side to become visible. However, consider that if we rotate the front side, 
we would be seeing the backside of the same card, not the actual other card. 
This is why we hover over the mid-container, which contains both the front and back sides.

When we hover over the mid-container, we apply the rotate property to both the mid-container itself and the backside card. 
What this means is that when the mid-container is hovered over, it rotates the first card by 180 degrees to reveal the back card. 

However, if we rotated the first card by 180 degrees, should we see the back card? 
No, because if we can't use the transform property within the back card, 
it won't be visible due to the first card hiding itself on the given rotation axis. 
This is why we use a total rotation of 360 degrees—180 degrees for the first side and the other 180 degrees for the back side.
If we didn't do this, we would only go halfway with a 180-degree rotation, resulting in an invisible back side.

Hope My Explanation understood by you.
