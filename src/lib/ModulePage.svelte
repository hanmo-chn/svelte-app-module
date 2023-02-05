<script lang="ts">
    import {fade} from "svelte/transition";
    import {onMount, tick} from "svelte";

    export let page;
    export let board;
    export let active: boolean = true;

    onMount(async ()=>{
        await tick();
    })

</script>
<div transition:fade="{{duration: 200 }}" class="tsui-stack-page-board" class:active>
    <div>
        <svelte:component this={page.component} {board} {...page.props} on:close/>
    </div>
</div>