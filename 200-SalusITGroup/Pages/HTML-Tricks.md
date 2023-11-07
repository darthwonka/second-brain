# HTML Tricks

Created: 2017-06-29 21:21:22 -0600

Modified: 2017-09-08 09:44:33 -0600

---

Javascript Back button.

<button type="button" onclick="javascript:history.back()">Back</button>

Centering Text with CSS

A side-effect of making the paragraph absolutely positioned is that it is then only as wide as it needs to be (unless we give it an explicit width, of course). In the example below, that's precisely what we want: We center a paragraph with just one word ("Centered!"), so the width of the paragraph should be exactly the width of that word.

Centered!

The yellow background is there to show that the paragraph is indeed only as wide as its contents. We assume the same mark-up as before:

<div class=container4>
<p>Centered!
</div>

The style sheet is similar to the previous example with respect to the vertical centering. But we now move the element halfway across the container as well, with 'left: 50%', and at the same time move it leftwards by half its own width in the 'translate' transformation:

div.container4 {

height: 10em;

position: relative }

div.container4 p {

margin: 0;

background: yellow;

position: absolute;

top: 50%;

**left: 50%;**

**margin-right: -50%;**

transform: translate(**-50%,** -50%) }

The next example below explains why the 'margin-right: -50%' is needed.

*From < <https://www.w3.org/Style/Examples/007/center.en.html#hv3>>*
