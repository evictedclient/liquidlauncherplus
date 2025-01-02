<script>
    import {exit} from "@tauri-apps/plugin-process";

    async function handleClick() {
        await exit(0);
    }
</script>

<button class="button-close" type="button" on:click={handleClick}>
    <img class="icon" src="img/icon/icon-button-close.svg" alt="close">
</button>

<style>
    .button-close {
        border-radius: 50%;
        height: 48px;
        width: 48px;
        background-color: transparent;
        border: solid 2px rgba(255, 255, 255, .5);
        box-shadow: 0px 0px 10px 1px rgb(255,255,255, .25);
        transition: ease background-color .2s;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
    }
    
    .button-close:hover {
        background-color: rgba(255, 255, 255, .1);
        box-shadow: 0px 0px 10px 1px rgb(255,0,0,.25);
    }
</style>