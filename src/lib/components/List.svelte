<script lang="ts">
	let props = $props();
</script>

<li>
    <a href="{props.link}">{props.title}</a>
</li>

<style>
    li{
        padding-bottom: 5px;
        font-size: 20px;
    }
    li:before {
        content: ">";
        padding-right: 5px;
    }  

    a{
        text-decoration: none;
        color: #c3c9da;
    }

    a:hover{
       color: #ffffff; 
       font-weight: bold;
    }
</style>
