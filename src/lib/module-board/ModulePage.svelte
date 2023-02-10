<script lang="ts">
    import {fade} from "svelte/transition";

    export let page;
    export let board;
    export let active: boolean = true;

</script>
<div transition:fade="{{duration: 200 }}" class="tsui-stack-page-board" class:active>
    <div>
        <svelte:component this={page.component} {board} {...page.props} on:close/>
    </div>
</div>