<script>
    import Service from "../../components/Service.svelte";
    export let data;
    const { services } = data;
</script>

<div class="pt-[70px] h-auto">
    <h1>Services Page</h1>

    {#each services as serv}
        <Service service={serv}/>
    {/each}
</div>