<script>
    let name;
    let beltColor;
    let age;
    // let fighting = false;
    // let sneaking = false;
    // let running = false;
    let skills = [];

    const handleSubmit = () => {
        console.log(name, beltColor, age);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="belt color" bind:value={beltColor}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting">Fighting<br>
    <input type="checkbox" bind:group={skills} value="sneaking">Sneaking<br>
    <input type="checkbox" bind:group={skills} value="running">Running<br>
    <label>Belt Color:</label>
    <select bind:value={beltColor}>
        <option value="black">Black</option>
        <option value="orange">Orange</option>
        <option value="brown">Brown</option>
        <option value="white">White</option>
    </select>
    <button>Add Person</button>
</form>

<style>

</style>