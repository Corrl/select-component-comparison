<script>
    import SlimSelect from "slim-select";
    import Infos from "./Infos.svelte";

    export let options = [{text: 'Value 1', value: 'value1'}];

    function initSlimSelect(selectElem) {
        new SlimSelect({
            select: selectElem,
            events: {
                afterChange(newVal) {
                    console.log('afterChange event - newVal: ', newVal)
                }
            }
        })
    }
</script>

<div class="select-component-wrapper">
    <Infos
            name="Slim Select 2.0"
            linkWebsite="https://slimselectjs.com/"
            linkGithub="https://github.com/brianvoe/slim-select"
    />
    <label for="slim-select-single">Single</label>
    <select id="slim-select-single"
            use:initSlimSelect
    >
        <option data-placeholder="true">Select your favorite framework</option>
        {#each options as option}
            <option value={option.value}>{option.text}</option>
        {/each}
    </select>

    <label for="slim-select-multiple">Multiple</label>
    <select id="slim-select-single"
            multiple
            use:initSlimSelect
    >
        <option data-placeholder="true">Select your favorite frameworks</option>
        {#each options as option}
            <option value={option.value}>{option.text}</option>
        {/each}
    </select>

</div>

<style>
    @import '../slimselect.css';
</style>