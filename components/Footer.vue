<template>
  <div class="container">
    <footer class="footer">
      <ul class="footer__list">
        <li class="footer__link">&copy;2021 GitHub, Inc</li>
        <li class="footer__link">Terms</li>
        <li class="footer__link">Privacy</li>
        <li class="footer__link">Security</li>
        <li class="footer__link">Status</li>
        <li class="footer__link">Docs</li>

        <div class="footer__logo">
          <img inline src="../assets/logo-light.svg" alt="" />
        </div>

        <li class="footer__link">Contact GitHub</li>
        <li class="footer__link">Pricing</li>
        <li class="footer__link">API</li>
        <li class="footer__link">Training</li>
        <li class="footer__link">Blog</li>
        <li class="footer__link">About</li>
      </ul>
    </footer>
  </div>
</template>

<script>
export default {};
</script>

<style>

footer {
	width: 100%;
	max-width: 81em;
	margin: auto;
	padding: 2em 1em 1em 1em;
	border-top: 1px solid #eaecef;
	margin-top: 4em;
	display: flex;
	align-items: center;
}

footer .footer__logo {
	display: none;
}

.footer__logo svg {
	fill: #eee;
}

footer .footer__list {
	flex: 1;
	font-size: 0.7rem;
	color: var(--color-text-secondary);
	display: flex;
	align-items: center;
	justify-content: center;
	flex-wrap: wrap;
	line-height: 2;
}

.footer__link {
	margin-right: 2em;
}
.footer__link:not(:first-child) {
	color: var(--link-color);
}
.footer__link:last-child {
	margin-right: 0;
}

@media (min-width: 868px) {
	footer {
		padding-left: 0;
		padding-right: 0;
	}

	footer .footer__logo {
		display: block;
		width: 2em;
	}

	.footer__logo svg {
		fill: #eee;
	}

	footer .footer__list {
		margin-left: 2em;
		justify-content: space-between;
	}
}


</style>
