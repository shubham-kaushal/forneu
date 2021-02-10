<template>
  <nu-block>
    <nu-theme hue="272" saturation="70" />
    <nu-props h1-font-size="2.5rem|||2rem" h1-line-height="3rem|||2.5rem" />
    <nu-attrs for="description" opacity=".8" />
    <nu-attrs for="grid" items="start stretch" gap="1gp" />

    <nu-block theme="special" :image="gradient">
      <Topbar />
      <SiteBlock
        badge="serverless framework · cms · eCommerce"
        heading="Build your web or mobile apps in minutes"
        description="Highly-scalable & highly-available out of the box."
        padding="10x 0||8x 0|4x 0 8x"
        level="1"
        fill="clear"
        special
        border="n"
      >
      </SiteBlock>
    </nu-block>

    <RuntimeTheming />

    <SiteBlock
      heading="Why Numl?"
      description="Another UI Framework? Why should anyone care?"
    >
      <nu-grid
        columns="1pr 1pr|||1fr"
        width="10sp||@content-width"
        text="left"
        items="stretch"
      >
        <nu-attrs for="card" padding="3x 4x|||2x" radius="3r" />

        <nu-card gap clear fill="bg" color="hue(15 pastel)">
          <nu-pane content="space-between" size="h3">
            <nu-h3>
              All-in-one
            </nu-h3>
            <nu-icon name="layers-outline" />
          </nu-pane>
          <nu-description>
            Numl is both a markup language for rapidly building responsive
            interfaces and a set of ready-to-use highly-customizable accessible
            elements. So you can use a single comprehensive tool to compose and
            style web applications. It's also possible to create simple
            interactions without writing JS.
          </nu-description>
        </nu-card>

        <nu-card gap clear fill="bg" color="hue(170 pastel)">
          <nu-pane content="space-between" size="h3">
            <nu-h3>
              Universal
            </nu-h3>
            <nu-icon name="flash-outline" />
          </nu-pane>
          <nu-description>
            Numl is built on top of Web Components, a modern web API to create
            reusable UI elements, and it's compatible with most modern
            JS-frameworks. You can use it as is or create lightweight wrappers
            for your favorite framework to improve DX, SSR and SEO.
          </nu-description>
        </nu-card>

        <nu-card gap clear fill="bg" color="hue(250 pastel)">
          <nu-pane content="space-between" size="h3">
            <nu-h3>
              Unique
            </nu-h3>
            <nu-icon name="bulb-outline" />
          </nu-pane>
          <nu-description>
            Numl is based on unique CSS generation technology that allows you to
            unleash all the power of modern CSS and take all styles under your
            control.
          </nu-description>
        </nu-card>

        <nu-card gap clear fill="bg" color="hue(290 pastel)">
          <nu-pane content="space-between" size="h3">
            <nu-h3>
              DX Focused
            </nu-h3>
            <nu-icon name="code-outline" />
          </nu-pane>
          <nu-description>
            Numl is focused on providing the best possible Developer Experience.
            It has lots of built-in helpers and solutions for routine UI
            development and its atomic approach is convenient for customization,
            maintaining, and refactoring.
          </nu-description>
        </nu-card>
      </nu-grid>

    <SiteBlock
      heading="Join the community"
      description="Your contribution and feedback will help us to constantly bring new&nbsp;awesome&nbsp;updates"
    >
      <nu-pane
        gap="1x"
        flow="row wrap"
        columns="||1pr 1pr"
        items="center"
        content="center"
        size="lg"
      >
        <nu-attrs
          for="btn"
          clear
          padding="1x 2x"
          color="special"
          shadow="no :hover[#shadow.33]"
        />
        <nu-btn to="!https://github.com/numldesign/numl">
          <nu-icon name="github-outline"></nu-icon>
          Github
        </nu-btn>
        <nu-btn to="!https://discord.gg/sHnHPnAPZj">
          <nu-icon name="message-circle-outline"></nu-icon>
          Discord
        </nu-btn>
        <nu-btn to="!https://twitter.com/numldesign">
          <nu-icon name="twitter-outline"></nu-icon>
          Twitter
        </nu-btn>
        <nu-btn to="!mailto:inbox@numl.design">
          <nu-icon name="email-outline"></nu-icon>
          eMail
        </nu-btn>
        <nu-btn to="!https://www.patreon.com/tenphi">
          <nu-icon name="heart-outline"></nu-icon>
          Sponsor
        </nu-btn>
      </nu-pane>
    </SiteBlock>
  </nu-block>
</template>

<script>
import RuntimeTheming from '@/components/landing/RuntimeTheming';
import SiteBlock from '@/components/global/SiteBlock';
import Snippet from '@/components/global/Snippet';
import Github from '@/helpers/github';
import App from '@/services/app';

export default {
  components: { Snippet, SiteBlock, RuntimeTheming },
  data() {
    const dev = process.client && location.hostname === 'localhost';

    return {
      App,
      githubStars: '...',
      nudeElementsLabel: `<nu-el color="text">nu</nu-el>de e<nu-el color="text">l</nu-el>e<nu-el color="text">m</nu-el>ents`,
      dev,
      syntaxSnippet: `
<nu-flex
  radius="2r" padding="2x"
  shadow gap content="space-between">
  <nu-block>It's sunny today.</nu-block>
  <nu-icon name="sun"></nu-icon>
</nu-flex>`,
      responsiveSnippet: `
<nu-block responsive="60rem|40rem">
  <nu-grid
    columns="repeat(4, 1fr)|1fr 1fr|1fr">
    ...
  </nu-grid>
</nu-block>`,
      stateSnippet: `
<nu-btn
  fill="bg :focus[special-bg]">
  Focus on me
</nu-btn>`,
    };
  },
  computed: {
    startSnippet() {
      return `
<script src="https://cdnjs.cloudflare.com/ajax/libs/numl/@${App.version}/index.js" type="module" />`;
    },
    gradient() {
      const hue = (mod) => {
        return (272 + 360 + mod) % 360;
      };
      const saturation = 70;

      return `linear(-20deg, hue(${hue(-15)} ${saturation} special), hue(${hue(
        15
      )} ${saturation} special))||linear(-40deg, hue(${hue(
        -10
      )} ${saturation} special), hue(${hue(10)} ${saturation} special))`;
    },
  },
  mounted() {
    Github.getStars('numldesign/numl').then(
      (stars) => (this.githubStars = stars)
    );
  },
};
</script>
