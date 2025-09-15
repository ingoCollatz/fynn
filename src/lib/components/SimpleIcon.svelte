<script lang="ts">
  import * as simpleIcons from "simple-icons";

  interface $$Props {
    name?: string;
    iconName?: string;
    title?: string;
    class?: string;
    className?: string;
    size?: string;
  }

  export let name: string = "";
  export let iconName: string = "";
  export let title: string = "";
  export let size: string = "24";
  export let className: string = "";
  let cssClass: string = "";
  export { cssClass as class };

  // Map icon names to Simple Icons exports
  const iconMap: Record<string, any> = {
    phone: simpleIcons.siLinphone,
    telephone: simpleIcons.siLinphone,
    linphone: simpleIcons.siLinphone,
    whatsapp: simpleIcons.siWhatsapp,
    gmail: simpleIcons.siGmail,
    email: simpleIcons.siGmail,
  };

  // Use either name or iconName prop
  $: actualIconName = name || iconName;
  $: icon = iconMap[actualIconName];
  $: finalClassName = className || cssClass;
</script>

{#if icon}
  <svg
    class={finalClassName}
    role="img"
    viewBox="0 0 24 24"
    xmlns="http://www.w3.org/2000/svg"
    fill="currentColor"
    style="width: {size}px; height: {size}px;"
  >
    {#if title}
      <title>{title}</title>
    {/if}
    <path d={icon.path} />
  </svg>
{/if}