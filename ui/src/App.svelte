<script lang="ts">
    import { onMount } from "svelte";

//onMount(() => { drawBoard()} );
class Sprite {
    x : number;
    y : number;
    width : number;
    height : number;


}


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

    /* squares */    
    context.rect(0,0,64,64);
    context.rect(128,0,64,64);
    context.rect(256,0,64,64);
    context.rect(256 + 128,0,64,64);

    for(let j = 0; j<8; j = j + 1) {    
        let even = j % 2;
        for(let i = 0;i<8; i = i + 2){
            context.rect(64*(i+even),64*j,64,64);
        }
    }
    context.fill();

    
    context.beginPath();
    context.fillStyle ="#0f0";
    for(let j = 0; j<8; j = j + 1) {
        let even = j % 2;
        for(let i = 0;i<8; i = i + 1){
            context.rect(64*i+36,64*j+34,8,8);
        }
    }
    context.fill();


    context.beginPath();
    context.fillStyle ="#f0f";
    for(let j = 0; j<8; j = j + 1) {
        let even = j %2;
        for(let i = 0;i<8; i = i + 1){
            context.rect(64*i+24,64*j+34,8,8,);
        }
    }
    context.fill();


    context.beginPath();
    context.fillStyle ="#ff0";
    for(let j = 0; j<8; j = j + 1) {
        let even = j %2;
        for(let i = 0;i<8; i = i + 1){
            context.rect(64*i+30,64*j+22,8,8,);
        }
    }
    context.fill();

    

}






</script>












<main>
<h2>WyvernChess</h2>


<canvas id="board" width=512 height=512></canvas>

<img id="spritesheet" style="display: none;" src="chess_sprites_Alpha.png" alt="spritesheet" on:load={drawBoard}/>

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
