<script>
// @ts-nocheck

  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";

</script>


<div>
    
    <Scroller layout="left">
    {#snippet sticky()}

    <h1>Hello</h1>
    <img src = "me.JPG" alt = "me">

        
    {/snippet}

    {#snippet scrolly()}
        <ArticleText>
            
        </ArticleText>
    {/snippet}
    </Scroller>
</div>  