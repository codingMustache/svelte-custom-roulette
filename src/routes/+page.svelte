<script>
  import { Wheel } from "../lib/index.js";

  /**
   * Represents a customizable roulette wheel component.
   * @typedef {Object} RouletteWheel
   * @property {string[]} label - An array of strings to display on the wheel.
   * @property {string[]} colors - An array of strings to map wheel-segment colors.
   */

  /**
   * RouletteWheel component.
   * @param {Object} options - Options for customizing the roulette wheel.
   * @param {string[]} [options.label=["yes", "no"]] - The strings to map to wheel-segments.
   * @param {string[]} [options.colors=["orange", "blue", "purple"]] - An array of strings to map wheel-segment colors.
   * @returns {RouletteWheel} The created roulette wheel component.
   */

  /**
   * `segmentsMap(n)`
   * @type {(n: string[]) => HTMLElement}
   * @param {string[]} [n=["yes", "no"]] - takes one argument defaulting to "yes" and "no" if not passed in
   * @returns {HTMLElement}
   */

  /**
   * `colorsMap(n)` items label
   * @type {(n: string[]) => void}
   * @param {string[]} [n=["orange", "blue", "purple"]] - takes one argument array of strings to map segment colors
   * @returns {void}
   */
  $: items = ["goodbye", "hello", "orange"];
  $: colors = ['red', 'green', 'blue']
  
  $: name = "";

  const addName = () => {
    items = [...items, name];
  };
</script>

<form on:submit={addName}>
  <input  bind:value={name} type="text" />
  <button type="button" on:submit={addName}>Add</button>
</form>

{#each items as item}
  <p>{item}</p>
{/each}

<Wheel {items} {colors} />
