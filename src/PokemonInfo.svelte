<script>
    import { onMount } from 'svelte';
  
    let pokemon = {
      name: '',
      image: '',
      height: '',
      weight: '',
      types: []
    };
    export let name = 'pikachu'; // Default to Pikachu if no name is provided


  onMount(async () => {
    const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${name}`);
    const data = await response.json();
    pokemon = {
        name: data.name,
        image: data.sprites.front_default,
        height: data.height,
        weight: data.weight,
        types: data.types.map((typeInfo) => typeInfo.type.name)
      };
  });
    // onMount(async () => {
    //   const response = await fetch('https://pokeapi.co/api/v2/pokemon/pikachu');
    //   const data = await response.json();
    //   pokemon = {
    //     name: data.name,
    //     image: data.sprites.front_default,
    //     height: data.height,
    //     weight: data.weight,
    //     types: data.types.map((typeInfo) => typeInfo.type.name)
    //   };
    // });
  </script>
  <div class="bg-white">
    
<img src="{pokemon.image}" alt="Pokemon" class="w-full" />
<div class="px-6 py-4 ">
  <div class="font-bold text-xl mb-2">Name: {pokemon.name.toUpperCase()}</div>
  <p class="text-gray-700 text-base">Height: {pokemon.height} decimetres</p>
  <p class="text-gray-700 text-base">Weight: {pokemon.weight} kilogram</p>
  <div class="tags">
    {#each pokemon.types as type}
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">{type}</span>
    {/each}
  </div>
</div>
</div>
<style>
    /* your styles go here */
</style>

<!-- markup (zero or more items) goes here -->