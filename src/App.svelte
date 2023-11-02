<script>
    import './app.css'
    import './own.css'

    import SlimSelect from "./lib/SlimSelect.svelte";
    import TomSelect from "./lib/TomSelect.svelte";

    const frameworks = ['angular', 'ember', 'meteor', 'react', 'solid', 'svelte', 'vue']

    const options = frameworks.map(value => {
        return {
            text: value[0].toUpperCase() + value.substring(1),
            value: value,
        }
    })

    function slimSelectOptions(values) {
        return values.map(value => {
            return {
                text: value[0].toUpperCase() + value.substring(1),
                value: value,
            }
        })
    }
</script>

<main>
    <h1>Select component comparison</h1>
    <p>See logs for change event information</p>

    <div id="select-wrapper">
        <SlimSelect {options}/>
        <TomSelect {options}/>
    </div>
</main>

<style>
    #select-wrapper {
        display: grid;
        grid-gap: 3rem;
        grid-template-columns: repeat(auto-fit, minmax(27rem, 1fr));
        /*border: 1px solid teal;*/
    }

    p {
        color: var(--svelte-orange);
        margin-bottom: 4rem;
        font-size: .9rem;
    }
</style>