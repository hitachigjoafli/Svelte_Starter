<script>
    import PokemonInfo from '../../PokemonInfo.svelte';
    let pokemonList = ['pikachu', 'bulbasaur', 'charmander', 'squirtle', 'eevee', 'jigglypuff', 'snorlax', 'psyduck', 'meowth', 'mewtwo'];
  </script>
  
  <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-4">
    {#each pokemonList as pokemon}
      <PokemonInfo name="{pokemon}" />
    {/each}
  </div>
  
  <style>
    /* Add any additional styling for your Pokédex page here */
  </style>