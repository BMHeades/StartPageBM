<script>
    import List from "./lib/List.svelte";

    export const prerender = true;


    // @ts-nocheck  

    class Item{
        constructor(title, link){
            this.title = title
            this.link = link
            // this.category = this.category
        }
    }

    // add your items here
    const items = [
        // title, link, category
        ["youtube", "https://www.youtube.com/", "other"],
        ["netflix", "https://www.netflix.com/browse", "other"],
        ["github", "https://github.com/", "dev"],
        ["boot.dev", "https://www.boot.dev/dashboard", "dev"],
        ["canvas", "https://tacomacc.instructure.com/", "study"],
        ["ctclink", "https://csprd.ctclink.us", "study"],
        ["sflix", "https://sflix.fi/", "other"],
        // ["netlify", "https://app.netlify.com/", "dev"],
        // ["wamap", "https://www.wamap.org/", "study"],
        // ["reddit", "https://www.reddit.com/", "other"]
        
    ]

    // start
    // let dev = $state([])
    // let study = $state([])
    // let other = $state([])

    const dev = []
    const study = []
    const other = []

    for(const item of items){
        switch(item[2]){
            case "dev":
                dev.push(new Item(item[0], item[1]))
                break;

            case "study":
                study.push(new Item(item[0], item[1]))
                break;

            case "other":
                other.push(new Item(item[0], item[1]))
                break;
        }
    }
    // console.log(dev)

</script>


<div class="big-padding">

    <!-- Big Welcome Text -->
    <div class="centered">
        <h1 class="big-welcome">~$hello!</h1>
    </div>

    <!-- Categories -->
    <div class="float-container">
        <!-- Dev -->
        <div class="float-child">
            <h2 class="centered">~/Dev</h2>
            <ul class="centered">
                {#each dev as item}
                    <List title = {item.title} link = {item.link}/>
                {/each}
            </ul>
        </div>


        <!-- Study -->
        <div class="float-child">
            <h2 class="centered">~/Study</h2>
            <ul class="centered">
                {#each study as item}
                <List title = {item.title} link = {item.link}/>
                {/each}
            </ul>
        </div>

    
        <!-- Other -->
        <div class="float-child">
            <h2 class="centered">~/Other</h2>
            <ul class="centered">
                {#each other as item}
                <List title = {item.title} link = {item.link}/>
                {/each}
            </ul>
        </div>
    </div>


</div>


<style>

    :global(body){
        background-color: #161b1e;
        color: #dce0eb;
        font-family: "Cascadia Code", sans-serif;
    }

    :global(a){
        text-decoration: none;
        color: #dce0eb;
    }
    .big-padding{
        margin: 15vw;
        margin-top: 110px;
        margin-bottom: 100px;
        /* background-color: red; */
    }

    .big-welcome{
        font-size: 7vw;
        /* background-color: red; */
    }

    .centered{
        margin-left: auto;
        margin-right: auto;
        width: 50%;  
        /* background-color: red; */
    }

    .float-container {
        /* border: 3px solid #fff; */
        /* padding: 20px; */
        /* background-color: red; */
        
    }
    .float-child {
        width: 33.333%;
        float: left;
        /* padding: 20pRecreationx; */
        /* border: 2px solid red; */
        /* background-color: red; */

    }  

    h2{
        font-size: 25px;
        color: #db92a7;
    }
    ul {
        /* margin-left: auto;
        margin-right: auto; */
       
        list-style-type: none; /* Remove bullets */
        padding: 0; /* Remove padding */
        margin: 0; /* Remove margins */
    }

    
</style>
