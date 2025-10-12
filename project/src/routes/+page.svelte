<script lang="ts">
    let interests = $state([]);
    function update(){
        interests.push(document.getElementById("interestsField").value);
    }
</script>

<h1>Welcome to my page!</h1>
<input type="text" id="interestsField"/>
<button id="button" onclick={update}>Enter Interest</button>
<p id="interestsParagraph">My interests are: {interests.reduce((a: string, b: string) =>a + b + ", ", "").slice(0, -2)}</p>