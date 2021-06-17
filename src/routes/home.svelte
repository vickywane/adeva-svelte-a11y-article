<script context="module">
    import "../assets/index.css"
    import Card from '../components/card.svelte'
    import Banner from '../components/banner.svelte'
    import * as Data from '../data.json'

    export async function preload(page, session) {
        return [   ]
    }
</script>

<svelte:head>
    <title>IWD 2021</title>
</svelte:head>

<div class="App" >
    <Banner />

    <div class="cards-body">

        <ul class="cards">
            {#each Data.heroes as heroine}
                <li>
                    <Card data={heroine}/>
                </li>
            {/each}
        </ul>
        <br />
        <br />

        <div class="align-center">
            <button
                    class="custom-btn"
                    style="background-color: transparent"
            >
                See More Heroines
            </button>
        </div>
        <br />
    </div>
</div>
