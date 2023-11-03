<script>
    import Select from 'svelte-select';
    import Infos from "./Infos.svelte";

    export let options = [];
    export let placeholder = '';

    function handleChange({detail}) {
        console.log('change event - detail:', detail)
    }
</script>

<div class="select-component-wrapper">

    <Infos name="Svelte Select"
           linkWebsite="https://svelte-select-examples.vercel.app/examples"
           linkGithub="https://github.com/rob-balfre/svelte-select"
    />

    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label>Single</label>
    <Select items={options}
            showChevron={true}
            on:change={handleChange}
            {placeholder}
    />

    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label>Multiple</label>
    <Select items={options}
            multiple
            clearable={false}
            on:change={handleChange}
            placeholder={placeholder + 's'}
    />

    <ul>
        <li>No option to mark search term..?</li>
        <li>Options not readable with dark mode</li>
    </ul>
</div>

<style>

</style>