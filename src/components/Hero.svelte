<script>
    import Image from "$lib/images/linkedin_bg.jpg";
</script>

<!-- TODO: Change the Hero page to have the image as the background 
     with a dark filter over it to see the text properly (YT Val video for reference) -->
<div class="h-screen w-full bg-blue-400 flex justify-around md:justify-between items-center flex-col md:flex-row">
    <div class="flex justify-center whitespace-nowrap items-center w-full md:w-1/2 text-[50px] font-bold">
        <h1>Fusion Auto Lab</h1>
    </div>
    <div class="md:w-1/2 w-full">
        <img src={Image} alt="Hero Page for Fusion Auto Lab" />
    </div>
</div>