<script lang="ts">
    import { onMount } from "svelte";

onMount(() => { drawBoard()} );

function drawBoard() {
    let canvas = document.getElementById("board") as HTMLCanvasElement;
    let context = canvas.getContext("2d");
    context.beginPath();
    context.rect(0,0,512,512);
    context.fill();
    
}



</script>












<main>
<h2>WyvernChess</h2>

<canvas id="board" width=512 height=512></canvas>


</main>







<style>

main {
     height: 100%;
}

canvas#board {
    border: 1px solid #000;
    width: 100%;
    aspect-ratio: 1/1;
    display: block;
}

@media (min-aspect-ratio: 1/1) {
       canvas#board {
                    width: auto;
                    height: 90%;
           
           aspect-ratio: 1/ 1;
           border: 1px solid #f00;
       }
}

</style>
