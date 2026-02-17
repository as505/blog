<div class="layout">
    <div class="frit-Contain">
        <div class="frit" id="frit0"></div>
        <div class="frit" id="frit1"></div>
        <div class="frit" id="frit2"></div>
        <div class="frit" id="frit3"></div>
    </div>
    <article class="text-background">
    </article>
    <div class="frit-Contain">
        <div class="frit" id="frit3-r"></div>
        <div class="frit" id="frit2-r"></div>
        <div class="frit" id="frit1-r"></div>
        <div class="frit" id="frit0-r"></div>
    </div>
</div>

<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
    
</script>
{@render children()}

<style>

:root{
    background-color: var(--col-content);
}

.layout{
    grid-template-columns: var(--blog-margin) auto var(--blog-margin);
    grid-template-rows: repeat(3, 100vh);
    width:90vw;
    height: 100vh;
    margin-left: auto;
    margin-right: auto;
    display: grid;
}

.frit-Contain{
    position: relative;
    display: flex;
}

.frit{
    position: absolute;
    height: 100%;
    background-color: rgba(0, 0, 0, 0);
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)70%, rgba(0, 0, 0, 0)70%);
    width: 4rem;
    background-repeat: repeat-y;
}

#frit1{
    right: -0.3rem;
    width: 1.4rem;
    background-position: 0rem 0rem;
}

#frit1-r{
    left: -0.3rem;
    width: 1.4rem;
    background-position: -2.6rem 0rem;
}

#frit2{
    right: 0.6rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)40%, rgba(0, 0, 0, 0)40%);
    background-position: 0.4rem 10rem;
}

#frit2-r{
    left: 0.6rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)40%, rgba(0, 0, 0, 0)40%);
    background-position: -0.4rem 10rem;
}

#frit3{
    right: 2.3rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)20%, rgba(0, 0, 0, 0)20%);
    background-position: 0.4rem 0rem;
}

#frit3-r{
    left: 2.3rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)20%, rgba(0, 0, 0, 0)20%);
    background-position: -0.4rem 0rem;
}

#frit0{
    right: -2rem;
    width: 2rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)20%, rgba(0, 0, 0, 0)20%);
    background-position: -1.0rem 0rem;
}


#frit0-r{
    left: -2rem;
    width: 2rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)20%, rgba(0, 0, 0, 0)20%);
    background-position: -1.0rem 0rem;
}

.text-background{
    background-color: var(--col-bg);
}

</style>