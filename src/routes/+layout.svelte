<script>
    import "../app.css";
    import Navbar from '../components/Navbar.svelte';
    import Footer from '../components/Footer.svelte';
</script>

<Navbar />
<div class="h-auto w-full">
    <div class="max-w-[1500px] m-auto px-4 bg-red-400">
        <slot />
    </div>
</div>
<Footer />