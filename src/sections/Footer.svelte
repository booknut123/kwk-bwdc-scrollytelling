<script>
  import Spacer from "../lib/Spacer.svelte";
  import Sources from "../lib/Sources.svelte";
</script>

<footer class="site-footer">
  <div class="footer-content">
    <p><strong>Made by Kailyn Lau</strong> — 2025</p>
    <p>
      This story is a work of narrative journalism built on publicly available
      data, including from the <a
        href="https://blackwealthdata.org"
        target="_blank">Black Wealth Data Center</a
      >, the U.S. Census Bureau, and more.
    </p>
    <p>Ari and Zora are fictional characters based on real experiences.</p>
    <details>
      <summary>Full sources</summary>
      <Sources />
    </details>
  </div>
</footer>

<style>
  .site-footer {
    background: #0e0e0e;
    color: #f0f0f0;
    padding: 3rem 1.5rem;
    text-align: center;
    font-size: 0.875rem;
    line-height: 1.5;
  }

  .footer-content {
    max-width: 700px;
    margin: 0 auto;
  }

  a {
    color: #ffd700;
    text-decoration: underline;
  }

  details summary {
    cursor: pointer;
    margin-top: 1rem;
    font-weight: bold;
  }
</style>
