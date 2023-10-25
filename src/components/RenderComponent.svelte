<script>
  export let bodyItem;
  export let compImage;
  export let Image2;
  export let Image3;
  export let RichText;

  import SectionWithImage from "./ImageLeftTextRight.svelte";
  import SimpleText from "./SimpleText.svelte";
  import ImageRightTextLeft from "./ImageRightTextLeft.svelte";
  import TripleImage from "./TripleImage.svelte";

  const components = {
    "image-with-text.section-with-image": SectionWithImage,
    "text.simple-text": SimpleText,
    "image-with-text.image-right-text-left": ImageRightTextLeft,
    "image-with-text.triple-image-below-text": TripleImage,
  };

  let extraProps = { compImage, RichText: bodyItem.RichText, Image2, Image3 };
</script>

<svelte:component
  this={components[bodyItem.__component]}
  {...bodyItem}
  {...extraProps}
/>
