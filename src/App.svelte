<script>
  import { fly, fade } from "svelte/transition";
  import About from "./About.svelte";
  import PhotoGrid from "./PhotoGrid.svelte";
  export let name;

  let about = false;
  let w;

  let btn = "About";

  function close() {
    about = false;
  }
</script>

<style>
  :global(body) {
    background-color: var(--whiteish);
    color: var(--slate);
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
  }

  h1,
  p {
    margin: 0;
    color: var(--slate);
  }

  :root {
    --slate: #262626;
    --grey-2: #3f3f3f;
    --whiteish: #f5f5f5;
    --lt-grey: #dcdcdc;
  }

  .sidebar {
    float: left;
    width: 19.1489%;
  }

  .content {
    float: right;
    width: 79.7872%;
    grid-row: 2/3;
    grid-column: 1/2;
  }

  /* make a grid */
  .wrapper {
    max-width: 940px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 2.5fr 1.5fr;
    grid-gap: 5px;
  }

  .wrapper > * {
    color: var(--slate);
    border-radius: 5px;
    padding: 20px;
    font-size: 150%;
    /* needed for the floated layout*/
    margin-bottom: 10px;
  }

  .header,
  .footer {
    grid-column: 1 / -1;
    /* needed for the floated layout */
    clear: both;
  }

  .header {
    grid-row: 1/2;
  }

  .sidebar,
  article {
    grid-row: 2/3;
  }

  .footer {
    grid-row: 3/4;
    font-style: italic;
  }

  blockquote.quote {
    color: var(--grey-2);
  }

  aside {
    padding: 0;
  }

  .sidebar {
    display: grid;
    grid-template-rows: 60px auto auto;
    grid-template-columns: 1fr;
  }

  .sidebar h1 {
    grid-column: 1/3;
    grid-row: 1/2;
  }
  .sidebar p {
    grid-row: 2/3;
    grid-column: 1/3;
    font-size: 1.1rem;
    padding: 1rem 0;
  }

  .sidebar p::first-letter {
    font-size: 2rem;
    line-height: 1rem;
    margin: 0;
    padding: 0;
    font-family: "Cormorant Garamond", serif;
  }

  .buy-now {
    max-width: 350px;
    /* height: 92px; */
    margin: auto;
    grid-column: 1/3;
    grid-row: 3/4;
    margin: 0;
  }

  .buy-now button {
    width: 100%;
    padding: 0.8rem 0;
    background-color: #fec84e;
    background-image: linear-gradient(0deg, #fec84e 0%, #ffdea8 74%);
    font-size: 1.2rem;
    border: 1px solid;
    margin-top: 2rem;
  }

  .header,
  nav {
    display: flex;
    justify-content: space-between;
  }

  .header button {
    border: none;
    background: none;
  }

  .header button:hover {
    text-decoration: underline;
  }

  h1 {
    font-weight: 300;
  }

  h1.name {
    text-align: right;
    font-weight: 400;
    font-size: 2.2rem;
  }

  h1 {
    font-family: "Cormorant Garamond", serif;
  }
  button.sm {
    display: none;
  }

  /* We need to set the widths used on floated items back to auto, and remove the bottom margin as when we have grid we have gaps. */
  @supports (display: grid) {
    .wrapper > * {
      width: auto;
      margin: 0;
    }
  }

  @media (max-width: 800px) {
    .wrapper {
      display: block;
    }

    .sidebar h1 {
      text-align: center;
    }

    .buy-now {
      display: flex;
      justify-content: center;
      width: 100%;
      max-width: unset;
    }

    .buy-now button {
      padding: 1rem 2rem;
    }

    .name-container {
      text-align: center;
      width: 75%;
      margin: auto;
    }

    .header {
      display: block;
    }
    nav {
      position: absolute;
      top: 0rem;
      right: 0rem;
    }

    button.sm {
      display: block;
    }

    button.bg {
      display: none;
    }

    .svg-container {
      width: 40px;
      height: 40px;
    }
  }

  @media (max-width: 500px) {
    .name-container {
      width: 80%;
      margin-left: 0;
    }
    .wrapper {
      padding: 5px;
    }

    h1.title {
      text-align: left;
    }

    h1.name {
      text-align: center;
      font-weight: 400;
      font-size: 2.2rem;
    }

    blockquote {
      font-size: 1rem;
      margin: 0;
    }
  }
</style>

<svelte:head>
  <link
    href="https://fonts.googleapis.com/css?family=Cormorant+Garamond:600|Spectral|Cormorant+Garamond|Cinzel+Decorative:400,900&display=swap"
    rel="stylesheet" />
</svelte:head>
<div class="wrapper" bind:clientWidth={w}>

  <header class="header" in:fade={{ duration: 700 }}>
    <div class="name-container">
      <h1 class="title">Holding On To Hope</h1>
      <h1 class="name">A Novel by R. B. Berry</h1>
    </div>
    <nav>
      <button class="bg" on:click={() => (about = true)}>About</button>
      <button class="sm" on:click={() => (about = true)}>
        <div class="svg-container">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path fill="none" d="M0 0h24v24H0V0z" />
            <path fill="#2f2f2f" d="M7 10l5 5 5-5H7z" />
          </svg>
        </div>
      </button>

    </nav>
  </header>
  {#if about === true}
    <About {close} />
  {/if}
  <article class="content">
    <div class="photo-grid">
      <PhotoGrid />
    </div>
  </article>

  <aside class="sidebar" in:fly={{ y: -400 }}>
    {#if about === true}
      <div class="overlay" />
    {/if}
    <h1>Available Now</h1>
    <p>
      Amid the escalation of the Vietnam War, a group of carefree college
      students at a Midwestern party school discover purpose and bonding
      relationships as anti-war activists when their school's former iconic
      basketball star is reported missing in action.
    </p>
    <div class="buy-now">
      <a
        href="https://www.amazon.com/gp/product/B07WRZ7TJM?pf_rd_p=183f5289-9dc0-416f-942e-e8f213ef368b&pf_rd_r=A0HSBKV7BKE614DQSV7D">
        <button>Buy Now On Amazon</button>
      </a>
    </div>
  </aside>

  <footer class="footer">
    <blockquote class="quote">
      "If you bring forth that which is within you
      <br />
      that which is within you
      <br />
      will save you."
      <br />
      -- The Gospel of Thomas
    </blockquote>

  </footer>
</div>
