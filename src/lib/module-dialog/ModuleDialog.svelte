<script lang="ts">

    import {fade} from "svelte/transition";

    export let component;
    export let isTop: boolean = true;
    export let props: any = null;
    export let board;

</script>

<div transition:fade class="tsui-app-module-dialog-board" class:transparent={isTop===false}>
    <div>
        <svelte:component this={component} {board} {...props} on:close/>
    </div>
</div>