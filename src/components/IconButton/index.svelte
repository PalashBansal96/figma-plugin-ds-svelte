<script>
    import Icon from './../Icon/index.svelte';

    export let iconName = '';
    export let iconText = null;
    export let selected = false;
    export let spin = false;
    export let tabindex = 0;
    export { className as class };

    let className = '';

</script>

<div on:click onclick="this.blur();" class:selected={selected} class="{className}" tabindex={tabindex}>
    {#if selected === true}
        <Icon {iconName} {iconText} {spin} color="white"/>
    {:else}
        <Icon {iconName} {iconText} {spin} color="black8"/>
    {/if}
</div>

<style>

    div {
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        width: var(--size-medium);
        height: var(--size-medium);
        border-radius: var(--border-radius-small);
        border: 2px solid transparent;
    }
    div:hover {
        background: var(--hover-fill);
    }
    div:active, div:focus {
        border: 2px solid var(--blue);
        outline: none;
    }

    .selected {
        background-color: var(--blue);
    }
    .selected:hover {
        background-color: var(--blue);
    }
    .selected:active, .selected:focus {
        border: 2px solid var(--black3);
    }

</style>