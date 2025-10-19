<script lang="ts">
    import Description from "./components/Description.svelte";
    import InterestField from "./components/InterestField.svelte";

    let interests:string[] = $state([]);
    let interestString = $derived(interests.reduce((a: string, b: string) =>a + b + ", ", "").slice(0, -2));
    function update(){
        let interestText = (document.getElementById("interestsField") as HTMLInputElement).value;
        if (interestText != null){
            interests.push(interestText);
        }
    }
    let obj = {title: "stuff", alt: "bla bla", description: "asdfj;alsdhgl"};
</script>

<h1>Welcome to my page!</h1>
<InterestField update = {update}/>
<Description {...obj} />
{#if (interests.length != 0)}
    <p id="interestsParagraph">My interests are: {interestString}</p>
{/if}
