<script lang="ts">
    import {createEventDispatcher} from "svelte";

    export let width: string = "600px";
    export let height: string = "400px";
    export let title: string = '';

    const dispatch = createEventDispatcher();

    export const close = () => {
        dispatch('close');
    }

</script>
<div class="tsui-module-dialog" style="width: {width}; height: {height}">
    <div class="dialog-title-bar">
        <div style="flex: 1 1 auto; white-space: nowrap; overflow: hidden; text-overflow: ellipsis">
            <span>{title}</span>
        </div>
        {#if $$slots['title-bar-icons']}
            <div class="title-bar-icons">
                <slot name="title-bar-icons"/>
            </div>
        {/if}
    </div>
    {#if $$slots['header']}
        <div class="dialog-header">
            <slot name="header"/>
        </div>
    {/if}
    <div class="dialog-content">
        <slot/>
    </div>
    <div class="dialog-control-bar">
        <slot name="control-bar">

        </slot>
    </div>
</div>