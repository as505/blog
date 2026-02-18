<div class="frit-Contain-r">
        <div class="frit" id="frit3-r"></div>
        <div class="frit" id="frit2-r"></div>
        <div class="frit" id="frit1-r"></div>
        <div class="frit" id="frit0-r"></div>
</div>

<style>
.frit-Contain-r{
        position: relative;
        display: flex;
        margin-right: auto;
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

#frit0-r{
    left: -2rem;
    width: 2rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)20%, rgba(0, 0, 0, 0)20%);
    background-position: -1.0rem 0rem;
}

#frit1-r{
    left: -0.3rem;
    width: 1.4rem;
    background-position: -2.6rem 0rem;
}

#frit2-r{
    left: 0.6rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)40%, rgba(0, 0, 0, 0)40%);
    background-position: -0.4rem 10rem;
}

#frit3-r{
    left: 2.3rem;
    background-size: 4rem 4rem;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)20%, rgba(0, 0, 0, 0)20%);
    background-position: -0.4rem 0rem;
}

</style>

