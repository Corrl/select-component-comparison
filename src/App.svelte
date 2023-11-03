<script>
    import './app.css'
    import './select-component-wrapper.css'

    import SlimSelect from "./lib/SlimSelect.svelte";
    import TomSelect from "./lib/TomSelect.svelte";
    import Choices from "./lib/Choices.svelte";
    import SvelteSelect from "./lib/SvelteSelect.svelte";

    const frameworks = ['angular', 'ember', 'meteor', 'react', 'solid', 'svelte', 'vue']

    const options = frameworks.map(value => {
        return {
            label: value[0].toUpperCase() + value.substring(1),
            text: value[0].toUpperCase() + value.substring(1),
            value: value,
        }
    })
</script>

<main>
    <h1>Select component comparison</h1>
    <p>See logs for change event information</p>

    <div id="select-wrapper">
        <SlimSelect {options}/>
        <TomSelect {options}/>
        <Choices {options}/>
        <SvelteSelect {options}/>
    </div>
</main>

<style>
    #select-wrapper {
        display: grid;
        gap: 3rem;
        grid-template-columns: repeat(auto-fit, minmax(27rem, 1fr));
        /*border: 1px solid teal;*/
    }

    p {
        margin-bottom: 5rem;
        color: #ff9400;
        font-size: .9rem;
        font-weight: bold;
    }
</style>