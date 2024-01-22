<script>
    import Icon from '@iconify/svelte';
    let mobileMenuState = false;

    const navLinks = [
        {
            link: "/",
            title: "Home"
        },
        {
            link: "/services",
            title: "Services"
        },
        {
            link: "/our-work",
            title: "Our Work"
        },
        {
            link: "/contact",
            title: "Contact"
        }
    ];
</script>

<div class="fixed w-full h-[70px] bg-red-400 text-white text-xl">
    <div class="max-w-[1500px] m-auto w-full bg-black h-full flex justify-between items-center px-4">
        <a class="font-semibold" href="/">Auto Fusion Lab</a>
        <div class="text-4xl md:hidden flex items-center">
            {#if mobileMenuState}
                <button on:click={() => mobileMenuState = !mobileMenuState}>
                    <Icon icon="ion:close" />
                </button>
            {:else}
                <button on:click={() => mobileMenuState = !mobileMenuState}>
                    <Icon icon="ion:menu" />
                </button>
            {/if}
        </div>
        <div class="hidden md:flex justify-between items-center font-semibold w-[400px]">
            {#each navLinks as link}
                <a href={link.link}>{link.title}</a>
            {/each}
        </div>
    </div>
</div>