<script>
    import { goto } from '@sapper/app'
    import "../assets/index.css"

    const handleRoute = async () => {
        await goto("/")
    }
</script>

<header class="header" >
    <nav>
        <h5 style="cursor:pointer;" on:click={() => handleRoute()} > IWD2020 </h5>
    </nav>
</header>