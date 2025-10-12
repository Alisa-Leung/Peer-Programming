<script lang="ts">
    import { onMount } from "svelte";
    let interests:string[] = $state([]);

    onMount(()=>{
        console.log("Mounted");
        document.getElementById("button")?.addEventListener("click", update);
    })

    function update(){
        let stuff = (document.getElementById("interestsField") as HTMLInputElement).value;
        if( stuff == null || stuff === "") return;
        interests.push(stuff);

    }
</script>

<h1>Welcome to my page!</h1>
<input type="text" id="interestsField"/>
<button id="button" >Enter Interest</button>
<p id="interestsParagraph">My interests are: {interests.reduce((a: string, b: string) =>a + b + ", ", "").slice(0, -2)}</p>