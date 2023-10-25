<script>
  export let bodyItem;
  export let compImage;

  import SectionWithImage from "./ImageLeftTextRight.svelte";
  import SimpleText from "./SimpleText.svelte";
  import ImageRightTextLeft from "./ImageRightTextLeft.svelte";
  import ImageLeftTextRight from "./ImageLeftTextRight.svelte";

  const components = {
    "image-with-text.section-with-image": SectionWithImage,
    "text.simple-text": SimpleText,
    "image-with-text.image-right-text-left": ImageRightTextLeft,
  };

  let extraProps = { compImage };
</script>

<svelte:component
  this={components[bodyItem.__component]}
  {...bodyItem}
  {...extraProps}
/>
