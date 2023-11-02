<script>
    import Infos from "./Infos.svelte";
    import TomSelect from "tom-select";
    import 'tom-select/dist/css/tom-select.default.css'

    export let options = [{value: "opt1", text: "Option 1"}];

    let placeholder = "Select your favorite framework";

    function initTomSelect(inputElem, config = {}) {
        const select = new TomSelect(inputElem, config)
        select.on('change', value => {
            console.log('change event - value:', value)
        })
        return {
            destroy() {
                select.destroy()
            }
        }
    }
</script>

<div class="select-component-wrapper">

    <Infos name="Tom Select"
           linkWebsite="https://tom-select.js.org/"
           linkGithub="https://github.com/orchidjs/tom-select"
    />

    <label for="slim-select-single">Single</label>
    <select id="slim-select-single"
            use:initTomSelect
    >
        <option value="">{placeholder}</option>
        {#each options as option}
            <option value={option.value}>{option.text}</option>
        {/each}
    </select>

    <label for="slim-select-multiple">Multiple</label>
    <select id="slim-select-single"
            multiple
            use:initTomSelect={{ plugins: { remove_button:{ title:'Remove this item'}}}}
    >
        <option value="">{placeholder + 's'}</option>
        {#each options as option}
            <option value={option.value}>{option.text}</option>
        {/each}
    </select>

    <ul aria-label="?">
        <li>Different styling of single/multiple element (background & arrow)</li>
        <li>Dropdown doesn't seem to adjust position based on available space</li>
        <li>Change event callback has only values, not option objects with all information</li>
    </ul>
</div>

<style>

</style>