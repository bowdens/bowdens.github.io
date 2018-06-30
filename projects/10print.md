---
layout: processingPage
title: "10PRINT"
---

<script type="text/javascript">
    function changeBGColour(id) {
        var pjs = Processing.getInstanceById(id);
        var rgb = document.getElementById('inputcolor').value;
        pjs.changeBGC(rgb);
    }
    function changeLineColour(id) {
        var pjs = Processing.getInstanceById(id);
        var rgb = document.getElementById('inputcolor').value;
        pjs.changeLineC(rgb);
    }
    function changeSize(id) {
        console.log("size changed to " + id)
        var pjs = Processing.getInstanceById(id);
        var len = document.getElementById('inputnum').value;
        pjs.changeSize(len);
    }
    function changeWeight(id) {
        var pjs = Processing.getInstanceById(id);
        var len = document.getElementById('inputweight').value;
        pjs.changeWeight(len);
    }
    function changeChance(id) {
        var pjs = Processing.getInstanceById(id);
        var len = document.getElementById('inputchance').value;
        pjs.changeHalfChance(len);
    }
</script>

<h1>Processing Page - 10PRINT</h1>


<canvas id="sketch" data-processing-sources="10print.pde"></canvas>

<p>
    <input type="color" value="000000" id="inputcolor"/><br>
    <button onclick="changeBGColour('sketch')">Change Background Colour</button><br>
    <button onclick="changeLineColour('sketch')">Change Line Colour</button>
</p>

<p>Change the size of the maze walls<br>
    <input type="range" min="4" max="100" value="50" onclick="changeSize('sketch')" id="inputnum"/>
</p>

<p>Change the weight of the maze walls<br>
    <input type="range" min="1" max="100" value="1" onclick="changeWeight('sketch')" id="inputweight"/>
</p>

<p>Change the chance of getting a half wall<br>
    <input type="range" min="0" max="100" value="0" onclick="changeChance('sketch')" id="inputchance"/>
</p>

<p>Based on Daniel Shiffman's video <a href="https://www.youtube.com/watch?v=bEyTZ5ZZxZs">Coding Challenge #76: 10PRINT in p5.js</a>.</p>

<p>The 10PRINT program was a single line BASIC program that prints out a maze pattern. The original line was <code>10 PRINT CHR$(205.5 + RND(1)); : GOTO 10</code></p>
<p>I have recreated this program in a processing sketch. There are a few settings you can change, as you can see above.</p>
