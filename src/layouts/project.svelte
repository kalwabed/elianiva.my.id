<style>
.project {
  max-width: 1080px;
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: repeat(3, minmax(min-content, max-content));
  grid-auto-flow: dense;
  align-items: flex-start;
  margin: 2rem auto;
  padding: 0 1rem;
  gap: 1rem;
}

.project__cover {
  grid-column: 1/2;
  width: 100%;
}

.project__wrapper {
  overflow: hidden;
  border: 0.0625rem var(--color-special-bg) solid;
}

.project__img {
  display: block;
  height: 100%;
  width: 100%;
}

.project__header {
  display: flex;
  gap: 1rem;
  align-items: center;
  margin-bottom: 1rem;
}

.project__title {
  color: var(--color-main-text);
  font-family: "Overpass", sans-serif;
  font-size: 2rem;
}

.project__buttons {
  display: flex;
  gap: 0.5rem;
}

.project__demo,
.project__source {
  font-family: "Open Sans", sans-serif;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.25rem 0.5rem;
  border-radius: 0.25rem;
  transition: filter ease-out 0.2s;
}

.project__demo:hover,
.project__source:hover {
  filter: brightness(1.2);
}
.project__demo {
  background-color: var(--color-main-accent);
  color: #ffffff;
}
.project__source {
  background-color: var(--color-special-bg);
  color: var(--color-alt-text);
}
:global(.project__icon) {
  width: 1.125rem;
  height: 1.125rem;
}
.project__divider {
  border: none;
  height: 0.125rem;
  margin: 0.5rem 0 1rem;
  background-color: var(--color-special-bg);
}

.project__content {
  grid-column: 1/2;
  font-family: "Open Sans", sans-serif;
  font-size: 1.125rem;
  line-height: 1.75rem;
}

.project__stack {
  grid-column: 2/3;
  grid-row: 1/-1;
  width: 100%;
  padding: 1rem;
  border: 0.0625rem var(--color-borders) solid;
}

.stack__title {
  color: var(--color-main-text);
  font-family: "Overpass", sans-serif;
  font-weight: 600;
  font-size: 1.5rem;
}

.stack__divider {
  height: 0.125rem;
  border: none;
  background-color: var(--color-borders);
  margin: 0.5rem 0;
}

.stack__item {
  display: grid;
  grid-template-columns: 3.5rem 1fr;
  gap: 1rem;
  align-items: center;
  padding: 1rem 0;
  border-bottom: 0.0625rem var(--color-borders) solid;
}

.stack__item:last-child {
  border: none;
}

.stack__logo {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0.5rem;
  border-radius: 0.5rem;
  background-color: var(--color-special-bg);
  overflow: hidden;
}

.stack__logo img {
  width: 100%;
}

.stack__name {
  color: var(--color-main-text);
  font-family: "Overpass", sans-serif;
  font-size: 1.25rem;
  text-decoration: none;
  transition: color ease-out 0.2s;
}

.stack__name:hover {
  color: var(--color-main-accent);
}

.stack__name::after {
  content: "↗";
  font-size: 1rem;
  vertical-align: top;
}

.project__content :global(p) {
  color: var(--color-main-text);
  margin-bottom: 1rem;
}

.project__content :global(p a) {
  position: relative;
  display: inline-block;
  color: var(--color-main-accent);
  text-decoration: none;
  margin: 0 0.125rem;
  transition: all ease-out 0.2s;
}

.project__content :global(p a::before) {
  position: absolute;
  content: "";
  bottom: 0;
  left: -0.25rem;
  right: -0.25rem;
  top: 0;
  transform: scale3d(0, 0.1, 1);
  transform-origin: 0 100%;
  background-image: linear-gradient(
    to right,
    var(--color-main-accent),
    rgba(0, 0, 0, 0)
  );
  z-index: -1;
  transition: transform ease-out 0.2s;
}

.project__content :global(img) {
  width: 100%;
  margin-top: 1rem;
}

.project__content :global(a:hover::before) {
  transform: scale3d(1, 0.1, 1);
}

.project__content :global(code) {
  font-family: "JetBrains Mono", monospace;
  color: var(--color-main-accent);
  padding: 0.125rem 0.25rem;
  font-size: 1rem;
}

.project__content :global(pre) {
  border-radius: 0.5rem;
  margin: 0.5rem 0;
  scrollbar-color: var(--color-thin) var(--color-special-bg);
  border: 0.125rem var(--color-borders) solid;
}

.project__content :global(pre::-webkit-scrollbar-thumb) {
  background-color: var(--color-thin);
}

.project__content :global(pre::-webkit-scrollbar) {
  background-color: var(--color-special-bg);
  height: 0.5rem;
}

.project__content :global(pre code) {
  padding: 0;
  border-radius: 0;
}

.project__content :global(blockquote p) {
  font-size: 1.125rem;
  letter-spacing: 0.02em;
  color: var(--color-alt-text);
  font-style: italic;
  font-family: serif;
  margin: 1rem 0;
}

.project__content :global(blockquote p::before) {
  content: "“	";
}

.project__content :global(blockquote p::after) {
  content: " ”";
}

@media only screen and (max-width: 480px) {
  .project__content :global(pre) {
    margin-left: -1rem !important;
    margin-right: -1rem !important;
    border-radius: 0;
  }
}

@media only screen and (max-width: 880px) {
  .project__cover {
    grid-column: 1/3;
  }

  .project__content {
    grid-column: 1/3;
  }

  .project__stack {
    grid-row: 2/3;
    grid-column: 1/3;
  }

  .project__header {
    flex-direction: column;
  }
}
</style>

<svelte:head>
  <link
    rel="preload"
    href="/prism-night-owl.css"
    as="style"
    onload="this.rel='stylesheet'"
  />
</svelte:head>

<SEO
  {title}
  {desc}
  thumbnail={`${data.siteUrl}/project/${currentSlug}/cover.webp`}
/>

<section class="project">
  <div class="project__cover">
    <div class="project__wrapper">
      <img
        src={`/assets/project/${currentSlug}/cover.webp`}
        alt={title}
        class="project__img"
        loading="lazy"
      />
    </div>
  </div>
  <div class="project__content">
    <div class="project__header">
      <h1 class="project__title">{title}</h1>
      <div class="project__buttons">
        {#if demo}
          <a
            class="project__demo"
            href={demo}
            target="_blank"
            rel="norel noreferrer"><Chrome class="project__icon" />Demo</a
          >
        {/if}
        <a
          class="project__source"
          href={source}
          target="_blank"
          rel="norel noreferrer"><Code class="card__icon" />Source</a
        >
      </div>
    </div>
    <hr class="project__divider" />
    <slot />
  </div>
  <div class="project__stack">
    <span class="stack__title">Tech Stack</span>
    <hr class="stack__divider" />
    {#each stack as item}
      <div class="stack__item">
        <div class="stack__logo">
          <img
            src="/assets/logo/{item[0].toLowerCase()}.png"
            alt={item}
            style="filter: {item[0].toLowerCase() === 'nextjs'
              ? 'var(--filter-invert)'
              : ''} "
          />
        </div>
        <a
          href={item[1]}
          class="stack__name"
          target="_blank"
          rel="norel noreferrer">{item[0]}</a
        >
      </div>
    {/each}
  </div>
</section>
<ProgressButton />

<script context="module">
export async function preload() {
  const projects = await (await this.fetch(`/api/project.json`)).json()
  return { projects }
}
</script>

<script>
import { stores } from "@sapper/app"
import SEO from "@/components/SEO.svelte"
import Chrome from "@/icons/chrome.svg"
import Code from "@/icons/code.svg"
import ProgressButton from "@/components/ProgressButton.svelte"
import data from "@/site-data"
export let title, desc, demo, source, stack

const { page } = stores()
const currentSlug = $page.path.split("/")[2]
</script>
