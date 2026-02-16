<div class="layout">
    <div class="frit-Contain">
        <div class="frit" id="frit0"></div>
        <div class="frit" id="frit1"></div>
        <div class="frit" id="frit2"></div>
        <div class="frit" id="frit3"></div>
    </div>
    <article class="text"></article>
    <div class="frit-Contain">
    </div>
</div>


<style>
.layout{
    grid-template-columns: 25vw 40vw 25vw;
    grid-template-rows: repeat(2, 100vh);
    width:90vw;
    height: 100vh;
    margin-left: auto;
    margin-right: auto;
    margin-top: auto;
    margin-bottom: 0px;
    display: grid;
    
}

.frit-Contain{
    position: relative;
}

.frit{
    position: absolute;
    height: 100%;
    background-color: rgba(0, 0, 0, 0);
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)70%, rgba(0, 0, 0, 0)70%);
    background-repeat: repeat-y;
}

#frit1{
    right: 0%;
    width: 20px;
    background-size: 40px 40px;
    background-position: 0px 0px;
}

#frit2{
    right: 3.5%;
    width: 40px;
    background-size: 40px 40px;
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)40%, rgba(0, 0, 0, 0)40%);
    background-position: 4px 20px;
}

#frit3{
    right: 8%;
    width: 40px;
    background-size: 40px 40px;
    background-image:  radial-gradient(circle, var(--col-content), var(--col-content)20%, rgba(0, 0, 0, 0)20%);
    background-position: 4px 0px;
}

#frit0{
    right: -5%;
    width: 40px;
    background-size: 40px 40px;
    background-image:  radial-gradient(circle, var(--col-bg), var(--col-bg)20%, var(--col-content)20%);
    background-position: 4px 0px;
}


.text{
    grid-area: "article";
    background-color: var(--col-content);
}

</style>