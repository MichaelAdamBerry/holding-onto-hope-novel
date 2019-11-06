<script>
  export let close;
</script>

<style>
  .about {
    grid-column: 1/2;
    grid-row: 2/3;
    justify-self: center;
    background-color: #fff9;
    margin: auto;
    z-index: 200;
    min-height: 100%;
    max-width: 700px;
    width: 100%;
    margin-top: 0;
  }

  .img-container {
    width: 200px;
    height: 200px;
    margin: 1rem;
    float: left;
    shape-outside: circle(50%);
    border-radius: 50%;
    overflow: hidden;
  }

  .about-card {
    margin: auto;
    background-color: var(--lt-grey);
    box-shadow: #2f2f2f33;
  }

  img {
    width: 100%;
    height: auto;
  }
  p {
    padding: 4rem;
  }

  button {
    background: none;
    border: none;
    font-size: 2rem;
    float: right;
    font-family: "Spectral", serif;
  }

  @media (max-width: 500px) {
    .about {
      width: 100vw;
    }

    p {
      padding: 1.2rem;
    }
  }
</style>

<div class="about">
  <slot>

    <div class="about-card">
      <button on:click={close}>ｘ</button>
      <div class="img-container">
        <img
          src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572975132/rbb_jegmxd.jpg"
          alt="R. B. Berry" />
      </div>
      <p>
        This is R. B. Berry's first novel. He has previously authored
        screenplays, short stories, and essays, as well as numerous articles for
        the Public Life Advocate. He served as President of the Public Life
        Foundation, a non-profit fostering local civic engagement. Born and
        raised in Kentucky, he is a fifth generation citizen of Owensboro -
        Daviess County, Kentucky. His wife, Joanne, is a retired school
        librarian. Sons Joe and Adam are both married. No grandkids. Just dogs
        and cats (who, as his sons remind him, are all very good boys and
        girls).
      </p>
    </div>

  </slot>

</div>
