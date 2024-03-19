<script>
    // let counter = 0;
  
    // function incrementCounter() {
    //   counter += 1;
    // }


  import { counter } from './store.js';

  function incrementCounter() {
    counter.update(n => n + 1);
  }

  </script>
  
  <div class="component-container bg-blue-500 text-white p-4">
    <!-- Component content will go here -->
    <button class="bg-blue-500 text-white p-2 rounded" on:click="{incrementCounter}">
        Click me
      </button>
      <!-- <p>Counter: {counter}</p> -->
      <p>Counter: {$counter}</p>
      
  </div>
  <style>
    /* Tailwind CSS utilities and custom styles */
  </style>
  