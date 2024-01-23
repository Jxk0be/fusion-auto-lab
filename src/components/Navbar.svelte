<script>
    import Icon from '@iconify/svelte';

    export let navLinks;
    let mobileMenuState = false;
</script>

<div class="fixed w-full h-[50px] md:h-[70px] bg-red-400 text-white text-xl z-20">
    <div class="max-w-[1500px] m-auto w-full bg-black h-full flex justify-between items-center px-4">
        <a on:click={() => mobileMenuState = false} class="font-semibold" href="/">Fusion Auto Lab</a>

        <!-- This is shown for mobile screens (menu/close buttons) -->
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

        <!-- This is shown for medium screens -->
        <div class="hidden md:flex justify-between items-center font-semibold w-[400px]">
            {#each navLinks as link}
                <a href={link.link}>{link.title}</a>
            {/each}
        </div>
    </div>
</div>

<!-- This is going to be only visible during mobile screens when the menu button is hit -->
<div class={`md:hidden flex bg-black text-xl text-white font-semibold fixed ${mobileMenuState ? 'top-0 duration-300 ease-in-out' : ' duration-300 ease-in-out top-[-300px]'}  pt-[50px] h-[250px] w-full`}>
    <div class="flex flex-col w-full h-full items-center justify-center">
        {#each navLinks as link}
            {#if link.title !== "Contact"}
                <div class="w-full border-b-2 border-[#eef6f3] text-left my-2">
                    <a class="pl-4" on:click={() => mobileMenuState = !mobileMenuState} href={link.link}>{link.title}</a>
                </div>
            {:else}
                <div class="w-full text-left my-2">
                    <a class="pl-4" on:click={() => mobileMenuState = !mobileMenuState} href={link.link}>{link.title}</a>
                </div>
            {/if}
        {/each}
    </div>
</div>