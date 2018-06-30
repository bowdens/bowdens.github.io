---
layout: processingPage
title: "Tree"
---
<script type="text/javascript">
    function setPlayers(id) {
        var pjs = Processing.getInstanceById(id);
        var players = document.getElementById('players').value;
        pjs.startGame(players);
    }
</script>

<h1>Processing Page - Dots and Boxes</h1>

<p>Start the game by choosing the number of players by either selecting it on the input button below, or by pressing it on the keyboard (while the game canvas is in focus).</p>

<canvas id="sketch" data-processing-sources="boxes.pde"></canvas>

<p>
    <input type="number" value="2" id="players" min="2" max="12"/>     <button onclick="setPlayers('sketch')">Set number of players (restarts game)</button>
</p>

<p>A processing implementation of the classic game Dots and Boxes. Each player takes turns drawing a line between dots. Score points by drawing a line that completes a box and if you do so, take another turn. The winner is the player at the end with the most boxes that they have completed.</p>
