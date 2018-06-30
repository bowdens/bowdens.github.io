---
layout: processingPage
title: "Tree"
---

<script type="text/javascript">
    function changeBGColour(id) {
        var pjs = Processing.getInstanceById(id);
        var rgb = document.getElementById('inputcolor').value;
        pjs.changeBGColour(rgb);
    }
    function changeDefaultLength(id) {
        var pjs = Processing.getInstanceById(id);
        var len = document.getElementById('length').value;
        pjs.changeDefaultLen(len);
    }
</script>

<h1>Processing Page - Tree</h1>

<p>A simple program that draws a tree each time you click the canvas.</p>

<canvas id="tree" data-processing-sources="tree.pde"></canvas>

<p>
    <input type="color" value="000000" id="inputcolor"/>
    <button onclick="changeBGColour('tree')">Change Background Colour</button>
</p>

<p>
    <input type="number" value="100" id="length"/>
    <button onclick="changeDefaultLength('tree')">Change Starting Length</button>
</p>

