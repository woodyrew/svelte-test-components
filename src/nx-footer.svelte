<svelte:options tag="nx-footer"/>

<script>
  export let year = new Date().getFullYear();
  export let showLicense;
</script>

<style lang="scss">
  @import "./style/settings";

  a {
    color: $c-black;
    font-size: 13px;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  a:hover {
    color: $c-blue;
  }

  .is-bg-grey {
    background: #f5f5f5;
  }

  footer {
    padding: 50px 20px;
  }

  .container {
    margin: 0 auto;
    max-width: 1600px;
  }

  .footer-icon {
    margin-bottom: 20px;

     svg {
      font-size: 36px;
      height: 36px;
      line-height: 1;
      width: auto;
    }
  }

  .legal-container {
    font-size: 11px;

    a {
      display: inline-block;
      font-size: 11px;
      margin-left: 2em;
    }
  }

  .row {
    display: flex;
    flex-wrap: nowrap;
  }

  @media (min-width: 640px) {
  }

  @media (min-width: 1024px) {
  }
</style>

<footer class="is-bg-grey">
  <div class="container">
    <div class="footer-icon">
      <a href="/" title="Go to xxx">
        <svg viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg"><rect fill="#73d2cf" class="nsvglogo-bg" width="16" height="16"></rect><path fill="#1f4cbf" class="nsvglogo-x" d="M3,3 5,3 13,11 13,13 11,13 3,5M3,13 3,11 11,3 13,3 13,5 5,13z"></path></svg>
      </a>
    </div>
    <div class="row">
      <slot></slot>
    </div>
    <div class="row row--last">
      <div class="columns small-12 medium-8 large-10 legal-container">
        <div class="has-top-bar has-top-bar--for-small">
          <strong>{year} &copy; XXX</strong>
          <a href="/legal/privacy-policy/">Privacy Policy</a>
          <a href="/about/gdpr/">Security</a>
          {#if showLicense}
            <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0; vertical-align: sub;" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png"></a>
          {/if}
        </div>
      </div>
    </div>

  </div>
</footer>
