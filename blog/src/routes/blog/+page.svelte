<script lang="ts">
	import MarginL from './margin-l.svelte';
    import MarginR from './margin-r.svelte';
</script>

<div class="layout">
    <MarginL></MarginL>
    <div class="bg">
        <article>
            <h1>
                Comparing methords to find the least number of bits required to represent an Integer number
            </h1>
            <hr>
            <p>
                Testing text
            </p>
        </article>
    </div>
    <MarginR></MarginR>
</div>

<style>

.bg{
    background-color: var(--col-bg);
}

hr{
    background-color: var(--col-highlight);
}

.layout{
    background-color: var(--col-content);
    grid-template-columns: var(--blog-margin) auto var(--blog-margin);
    grid-template-rows: repeat(3, 100vh);
    width:100vw;
    height: 100vh;
    margin-left: auto;
    margin-right: auto;
    display: grid;
}


article{
    width: 90%;
    margin: auto;
}


</style>