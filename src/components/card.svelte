<script>
    import "../assets/index.css"
    import {goto} from '@sapper/app'

    const handleRouting = async (name) => {
        await goto(`/${name}`)
    }

    export let data;
 </script>

<div style="margin: 0 4rem;">
    <div class="align-center">
        <img  alt={data.name}
                class="img"
                src={data.img_uri}/>
    </div>
    <br/>
    <p> {data.name}</p>
    <p>
        {data.description}
    </p>
    <br/>

    <div class={"align-center"}>
        <button
                on:click={() => handleRouting(data.name)}
                class="custom-btn"
        >
            Read Biography
        </button>
    </div>
</div>