<template>
  <nu-header
    width="--content-width"
    space="around"
    padding="4x 1cp||2x 1cp"
    fill="clear"
  >
    <nu-pane content="space-between" size="md" flow="row|||column" gap="2x 1x">
      <nu-pane text="nowrap">
        <nu-svg src="/images/forneu-logo-small.svg" height="36.56px" width="121px" />
      </nu-pane>
      <nu-pane size="lg" gap="0|||1x">
        <nu-attrs for="btn" padding="1x 2x|||1x" />
        <nu-attrs for="icon" show="y||||n" />
        <nu-btn clear to="!https://www.instagram.com/forneuhq">
          <nu-icon name="logo-instagram" />
          Instagram
        </nu-btn>
        <nu-btn clear to="https://www.facebook.com/forneuhq">
          <nu-icon name="logo-facebook" />
          Facebook
        </nu-btn>
        <nu-btn clear to="!https://twitter.com/forneuhq">
          <nu-icon name="logo-twitter" />
          Twitter
        </nu-btn>
      </nu-pane>
      <!--      <nu-block>-->
      <!--        <nu-inputgroup radius="round">-->
      <!--          <nu-icon name="search-outline"></nu-icon>-->
      <!--          <nu-search />-->
      <!--        </nu-inputgroup>-->
      <!--      </nu-block>-->
    </nu-pane>
  </nu-header>
</template>
