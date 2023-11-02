<script>
    import SlimSelect from "slim-select";
    import Infos from "./Infos.svelte";

    export let options = [{text: 'Value 1', value: 'value1'}];

    function initSlimSelect(selectElem) {
        new SlimSelect({
            select: selectElem,
            settings: {
                searchHighlight: true,
            },
            events: {
                afterChange(newVal) {
                    console.log('afterChange event - newVal:', newVal)
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

    <ul aria-label="?">
        <li>Same highlighting of already selected and currently selected item in list</li>
        <li>Selected options not removed from list - would be better? -> option to enable?</li>
        <li>'selected: false' on last selected option object (see event log)</li>
        <li>Focus styling not visible with dark theme</li>
    </ul>
</div>

<style>
    @import '../slimselect.css';

    p {
        margin-top: 2rem;
    }
</style>