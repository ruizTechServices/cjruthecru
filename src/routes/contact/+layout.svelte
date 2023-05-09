<script>
    import "../app.css";
    import Navbar from "../../components/navbar.svelte";

</script>
<div class="parent">
    <div class="div1">
        <header>
            <Navbar />
        </header>
    </div>
    <div class="div2">
        <slot />
    </div>
    <div class="div3">

    </div>
</div>
<style>
    .parent {
        display: grid;
        grid-template-columns: repeat(12, 1fr);
        grid-template-rows: repeat(12, 1fr);
        grid-column-gap: 0px;
        grid-row-gap: 0px;
    }

    .div1 {
        grid-area: 1 / 1 / 3 / 13; 
    }
    .div2 {
        grid-area: 4 / 3 / 10 / 10; 
    }
    .div3 {
        grid-area: 11 / 1 / 13 / 13; 
    }
</style>

