<script>

</script>

<style>
  .photo-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-rows: auto;
    transform: translate(0, 3rem);
  }

  .bg {
    grid-row: 1/5;
    grid-column: 1/5;
    width: 95%;
    height: 95%;
    align-self: center;
    justify-self: center;
    filter: grayscale(0.7);
  }
  .one img,
  .two img,
  .three img,
  /* .four img {
    box-shadow: 5px 0px 10px #2f2f2f;
  } */
  .one {
    grid-row: 1/3;
    grid-column: 1/3;
    width: 100%;
    justify-self: center;
    align-self: center;
    opacity: 0.99;
    transform: rotate(345deg);
    transform-origin: bottom;
  }

  .two {
    grid-row: 1/5;
    grid-column: 2/5;
    opacity: 0.99;
    width: 53%;
    justify-self: center;
    filter: url(#blur);
    transform: rotate(9deg);
  }

  .three {
    grid-row: 3/5;
    grid-column: 1/3;
    opacity: 0.99;
    width: 100%;
    justify-self: center;
    z-index: 500;
    transform: rotate(2deg);
  }

  /* .four {
    grid-row: 3;
    grid-column: 3/5;
    opacity: 0.99;
    width: 82%;
    justify-self: right;
    z-index: 500;
    transform: rotate(-4deg);
  } */

  img {
    width: 100%;
    height: auto;
  }

  @media (max-width: 800px) {
    .photo-grid {
      transform: translate(50px, 0);
      margin: 50px 0 40px 0;
    }
  }
</style>

<filter
  id="blur"
  x="0%"
  y="0%"
  width="140%"
  height="240%"
  filterUnits="objectBoundingBox"
  primitiveUnits="userSpaceOnUse"
  color-interpolation-filters="linearRGB">
  <feGaussianBlur
    stdDeviation="0 3"
    x="0%"
    y="0%"
    width="100%"
    height="100%"
    in="SourceGraphic"
    edgeMode="wrap"
    result="blur" />
</filter>

<div class="photo-grid">

  <div class="bg">
    <!-- <img
      src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572915150/annelies-geneyn-bhBONc07WsI-unsplash_qer6qe.jpg"
      alt="" /> -->
  </div>

  <div class="two">
    <img
      src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572985169/1961_JerryLucas_original__fliter--red-sunset__channel--all__mode--hard-light_kh2ihc.png"
      alt="" />
  </div>
  <div class="one">
    <img
      src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572985149/vietnam-img__fliter--red-sunset__channel--all__mode--multiply_gxxfk3.png"
      alt="" />
  </div>
  <div class="three">
    <img
      src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572994734/students__fliter--red-sunset__channel--all__mode--color-burn_w2xrsr.png"
      alt="" />
  </div>
  <!-- <div class="four">
    <img
      src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572994116/sit-in__fliter--red-sunset__channel--red__mode--multiply_h2wypz.png"
      alt="" />
  </div> -->

</div>
