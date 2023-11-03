<script>
    import Infos from "./Infos.svelte";
    import Choices from "choices.js";
    import 'choices.js/public/assets/styles/choices.css'

    export let options = [];
    export let placeholder = '';

    function initChoices(selectElem) {
        const config = {
            removeItemButton: true,
        }
        const choices = new Choices(selectElem, config);

        selectElem.addEventListener('change', handleChange)

        function handleChange() {
            console.log('change event - current value:', choices.getValue())
        }

        return {
            destroy() {
                choices.destroy()
            }
        }
    }
</script>


<div class="select-component-wrapper">
    <Infos
            name="Choices"
            linkWebsite="https://choices-js.github.io/Choices/"
            linkGithub="https://github.com/Choices-js/Choices"
    />

    <label for="slim-select-single">Single</label>
    <select id="slim-select-single"
            use:initChoices
    >
        <option value="">{placeholder}</option>
        {#each options as option}
            <option value={option.value}>{option.label}</option>
        {/each}
    </select>

    <label for="slim-select-multiple">Multiple</label>
    <select id="slim-select-single"
            multiple
            use:initChoices
    >
        <option value="">{placeholder + 's'}</option>
        {#each options as option}
            <option value={option.value}>{option.label}</option>
        {/each}
    </select>

    <ul>
        <li>
            Placeholder of single and multiple styled differently
        </li>
        <li>
            Placeholder remains in select even when option is selected - good/helpful?
        </li>
        <li>
            No option to highlight search term?
        </li>
        <li>
            Options not readable with dark mode
        </li>
    </ul>
</div>
<style>
    /*noinspection CssUnusedSymbol*/
    :global(.choices) {
        margin-bottom: 0;
    }
</style>