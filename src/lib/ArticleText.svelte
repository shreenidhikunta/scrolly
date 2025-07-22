<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children?.()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        background-color: #eb6a61;
        color: #ffffff;
        border: solid #ffffff 3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 16px 16px rgb(168, 44, 44);
    }
</style>
