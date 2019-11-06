<script>

</script>

<style>
  .vert {
    filter: url("#blur");
  }
</style>

<filter
  id="blur"
  x="-20%"
  y="-20%"
  width="140%"
  height="140%"
  filterUnits="objectBoundingBox"
  primitiveUnits="userSpaceOnUse"
  color-interpolation-filters="linearRGB">
  <feGaussianBlur
    stdDeviation="0 12"
    x="0%"
    y="0%"
    width="100%"
    height="100%"
    in="SourceGraphic"
    edgeMode="wrap"
    result="blur" />
</filter>

<div class="vert">
  <img
    src="https://res.cloudinary.com/dscjol9s7/image/upload/v1572985169/1961_JerryLucas_original__fliter--red-sunset__channel--all__mode--hard-light_kh2ihc.png"
    alt="" />
</div>
