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
            <h3 class="example">
                Example:<br>
                If the code dictionary only has 2 entries, a single bit is enough to refer to all indexes. 
                When a third entry is added to the dictionary, each subsequent code needs atleast 2 bits to refer to any entry.
            </h3>
            <p>
                As more entries are added to the dictionary, more bits are needed to index it. 
                Therefore, to implement Gif LZW, we need a way to get the exact number of bits needed to represent any number.
            </p>
            <hr>
            <p>
                N^2 represents the largest possible number that N bits can describe, so
                our problem can be described as:
            </p>
            <h3>
                For any number M, what is the smallest number N, where N^2 &gt= M;
            </h3>
            <p>
                For fun, and a little curiosity, I wrote and compared 3 functions, 
                comparing them to see if there were any noticable differences in performance.
            </p>
            <hr>
            <h2>
                The experiment
            </h2>
            <p>
                The first function uses a 32 bit integer, where all the bits are set to 1.
                In a loop, the integer is bitshifted to the right until only one digit remain.
                The amount of digits remaining is increased by one digit each iteration of the loop,
                until we have a value greater than or equal to the input.
            </p>
            <p>
                The seccond function attempts to use a binary search to reduce the number of iterations in the loop.
                Instead of including one more digit each iteration, it instead tries to include 16 digits.
                I call these bits the pivot.
                If 16 digits is too big of a jump, it halves the pivot to 8 bits, then 4, 2, and finaly 1 bit.
                Instead of returning when the bitshifted value &gt= input, it returns when the pivot is reduced to 0 bits.
            </p>
            <p>
                The final function is a simple loop where an int is raised to the power of 2.
                As long as this equation gives a number smaller than the input, we increment the int by 1.
            </p>
            <p>
                Since we can pass pointers to functions in C, we can write a function to time the execution of any given function.
                To get a measurable number in MS, we run each function several thousands of times.
                Each of the thousands of runs we generate a random Int as the input.
                The functions generating the random integers can also be customized to favor smaller or larger numbers,
                so we can test how the performance is affected by the size of the input int.
            </p>
            <hr>
            <h2>
                Results
            </h2>
            <hr>
            <h2>
                Conclusion
            </h2>
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

h2{
    color: var(--col-header);
    font-size: 2.5rem;
}

h3{
    color: var(--col-header);
    font-size: 1.5rem;
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