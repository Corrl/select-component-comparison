<script>
    import './app.css'
    import './own.css'

    import SlimSelect from "./lib/SlimSelect.svelte";

    const frameworks = ['angular', 'react', 'svelte', 'vue']

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

    <SlimSelect options={slimSelectOptions(frameworks)}/>
</main>

<style>

</style>