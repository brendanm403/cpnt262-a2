<script>
  export let heading = "Product Name";
  export let description = "a short descriptionabout the product";
  export let src;
  export let alt = "an image";
  export let href = "/products";
</script>

<a {href}>
  <article class="max-w-fit bg-surface-200-700-token rounded-container-token px-2 py-3 border-token border-surface-600-300-token">
    <img class="block w-64 h-64 mx-auto rounded-container-token" {src} {alt}>
    <h3 class="my-3">{heading}</h3>
    <p class="my-3">{description}</p>
  </article>
</a>
