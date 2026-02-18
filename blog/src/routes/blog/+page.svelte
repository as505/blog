<script lang="ts">
	import MarginL from './margin-l.svelte';
    import MarginR from './margin-r.svelte';
</script>

<div class="layout">
    <MarginL></MarginL>
    <div class="bg">
        <article>
            <h1>
                Finding the least number of bits required to represent an Integer in C
            </h1>
            <hr>
            <p>
                Im currently working on writing an encoder to create Gif files, which means I need to implement the compression algorithm used in the Gif format.
                To save space, Gif files use a variant of LZW compression to reduce the size of their image data.
                Instead of sending the raw data we can instead send a series of indexes into this dictionary, and let a decoder reconstruct the original data.
            </p>
            <p>
                LZW algorithms works by creating a dictionary of 'codes' that describe patterns found in the input.
                The LZW implementation for Gif files use variable length codes to ensure as few bits of data are used as possible.
            </p>
            <h2 class="example">
                Example:<br>
                If the code dictionary only has 2 entries, a single bit is enough to refer to all indexes. 
                When a third entry is added to the dictionary, each subsequent code needs atleast 2 bits to refer to any entry.
            </h2>
            <p>
                As more entries are added to the dictionary, more bits are needed to index it. 
                Therefore, to implement Gif LZW, we need a way to get the exact number of bits needed to represent any number.
            </p>
            <hr>
            <p>
                N^2 represents the largest possible number that N bits can describe, so
                our problem can be described as:
            </p>
            <h2>
                For any number M, what is the smallest number N, where N^2 &gt= M;
            </h2>
            <p>
                For fun, and a little curiosity, I wrote and compared 3 functions to do this, 
                comparing them to see if there were any noticable differences in performance.
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

h1{
    font-size: 3rem;
    margin-bottom: 2rem;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
}

p{
    font-size: 2rem;
}

.layout{
    background-color: var(--col-content);
    grid-template-columns: var(--blog-margin) auto var(--blog-margin);
    width:99vw;
    min-height: 100vh;
    margin-left: auto;
    margin-right: auto;
    display: grid;
}


article{
    height: auto;
    width: 80%;
    margin: auto;
    margin-top: 6rem;
    margin-bottom: 0rem;
}

:global(body){
    margin-bottom: 0rem;
}


</style>