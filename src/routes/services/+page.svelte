<script>
    import Service from "../../components/Service.svelte";
    import services from "$lib/data/services.json";
</script>

<div class="pt-[70px] h-auto">
    <h1>Services Page</h1>

    {#each services as serv}
        <Service service={serv}/>
    {/each}
</div>