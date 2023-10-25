<script>
  export let component;
  export let extraData; // New prop

  import SectionWithImage from "./SectionWithImage.svelte";
  import SimpleText from "./SimpleText.svelte";
  import ImageRightTextLeft from "./ImageRightTextLeft.svelte";

  const components = {
    "image-with-text.section-with-image": SectionWithImage,
    "text.simple-text": SimpleText,
    "image-with-text.image-right-text-left": ImageRightTextLeft,
  };

  let extraProps = {};

  if (component.__component === "image-with-text.section-with-image") {
    extraProps.imageUrl = extraData.imageUrl; // Using extraData
    extraProps.compImage = extraData.compImage; // Add this line to include compImage
    extraProps.body = component.Body; // Replace this with the actual field
  }
</script>

<svelte:component
  this={components[component.__component]}
  {...component}
  {...extraProps}
/>
