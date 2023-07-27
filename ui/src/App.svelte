<script lang="ts">
    import { onMount } from "svelte";

onMount(() => { drawBoard()} );

function drawBoard() {
    let canvas = document.getElementById("board") as HTMLCanvasElement;
    let context = canvas.getContext("2d");

    /* Background */
    context.beginPath();
    context.fillStyle ="#000";
    context.rect(0,0,512,512);
    context.fill();

    /* Lines */
    context.beginPath();
    context.fillStyle ="#fff";
    for(let i = 1; i<8; i = i + 1) {
        context.rect(0,64*i,512,1);
    }
    for(let i = 1; i<8; i = i + 1){
        context.rect(64*i,0,1,512);
    }

    

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
