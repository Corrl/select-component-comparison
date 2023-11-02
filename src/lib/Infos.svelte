<script>
    export let name = '';
    export let linkWebsite = '';
    export let linkGithub = '';

</script>


<div class="infos">
    <h2>{name}</h2>
    <div class="links">
        <a href={linkWebsite} target="_blank">🔗 website</a>
        <a href={linkGithub} target="_blank">🔗 github</a>
    </div>
</div>

<style>
    .infos {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>