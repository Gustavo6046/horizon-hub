<!-- Main.svelte -->
<script>
    import jquery from 'jquery';
    import { onMount } from 'svelte';

    let button = jquery("#App-counter-button");
    let counter = 0;

    function count() {
        counter += 1;

        jquery("#App-counter-button").html("Count: " + counter);
    }

    onMount(async () => {
        jquery("#App-counter-button").click(count);
    });
</script>

<style type="text/scss">
    #App-counter-button {
        width: 200px;
        height: 50px;
        border-radius: 5px;
        background-color: #eee;
        color: black;

        :hover {
            background-color: #aae;
        }

        :active {
            background-color: #224;
            color: white;
        }
    }

    document, body {
        margin: 0px;
        padding: 0px;
    }

    body {
        // style
        background-color: #555;

        // layout
        display: flex;
        flex-direction: column;
    }
</style>

<div class="App">
    <header class="App-header">
        Click here to count!
        <button id="App-counter-button">Count: 0</button>
    </header>
</div>