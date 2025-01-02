<script>
    export let text;
</script>

<div class="text-status">{text}</div>

<style>
    .text-status {
        color: white;
        text-shadow: #f00 0px 0px 10px;
        align-items: stretch;
        display: flex;
        align-items: center;
        border-bottom: solid 2px rgb(165, 0, 0);
        width: max-content;
        margin: 0 auto;
    }
</style>