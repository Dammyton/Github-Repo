<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>

:root {
	--border-color: #e1e4e8;
	--border-alternate-color: #444d56;
	--header-bg-color: #24292e;
	--link-color: #0366d6;
	--color-text-primary: #24292e;
	--color-text-secondary: #586069;
	--nav-primary-text-color: #fff;
	--tab-counter-color: #d1d5da80;
}

*,
*::before,
*::after {
	font-family: inherit;
	font-size: inherit;
	box-sizing: inherit;
	text-decoration: none;
	line-height: inherit;
}

html {
	box-sizing: border-box;
	scroll-behavior: smooth;
}

body {
	background: #fff;
	font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
		Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
	min-height: 100vh;
	color: var(--color-text-primary);
	padding: 0;
	margin: 0;
	line-height: 1.5;
	overflow-x: hidden;
}

a {
	color: inherit;
	text-decoration: none;
}

ul {
	margin: 0;
	padding-left: 0;
	list-style: none;
}

button {
	cursor: pointer;
	text-decoration: none;
	border: 0;
	border-radius: 6px;
	font-size: 1rem;
	display: inline-block;
	color: #fafbfc;
  background: #25292e;
}
button:focus {
	outline: none;
}

img {
	max-width: 100%;
	height: auto;
	object-fit: cover;
}

.avatar__thumbnail {
	border-radius: 50%;
	width: 1.3em;
}

.status__text {
	margin-left: 0.3em;
	overflow: hidden;
	white-space: nowrap;
	text-overflow: ellipsis;
}

.status__container {
	padding: 0.7em;
	border-bottom: 1px solid var(--border-color);
	margin-bottom: 0.6em;
}

.status {
	display: flex;
	font-size: 0.8rem;
	border: 1px solid var(--border-color);
	border-radius: 6px;
	padding: 0.5em;
}

/* Status text & emoji on desktop view */
@media (min-width: 868px) {
	.status__mobile {
		display: none;
	}
}

.main {
	display: grid;
	grid-template-columns: 1fr;
	grid-gap: 1em;
	margin-top: 1em;
	margin-left: 3em;
	margin-right: 3em;
}

/* PROFILE SECTION */
/* .profile__info {
	padding-left: 1em;
	padding-right: 1em;
	position: relative;
} */

.profile__info .about {
	display: flex;
	align-items: center;
	flex-wrap: wrap;
}

.profile__info .avatar {
	width: 6em;
	position: relative;
	margin-right: 1.4em;
	margin-bottom: 0.5em;
}

.profile__info #profile__img {
	width: 100%;
	height: auto;
	border-radius: 50%;
	border: 1px solid var(--border-color);
}

.profile__info .dart {
	display: none;
	border: 1px solid var(--border-color);
	border-radius: 2em;
	padding: 6px 10px;
	position: absolute;
	bottom: 17%;
	left: 87%;
	background: #fff;
	cursor: pointer;
	transition: 0.5s ease;
}

.dart .status__message {
	display: none;
	font-size: 0.7rem;
	transition: 0.5s ease;
	margin-left: 0.4em;
}

.profile__info .metadata .name {
	font-size: 1.6rem;
	font-weight: 600;
	text-transform: capitalize;
	margin-bottom: 0;
	margin-top: 0;
}

.metadata .username {
	font-size: 1.2rem;
	font-weight: 300;
	color: var(--color-text-secondary);
	margin-bottom: 0;
	margin-top: -0.2em;
}

.profile__info .bio {
	line-height: 1.5;
}

.profile__info .edit__btn {
	display: block;
	width: 100%;
	text-align: center;
	border: 1px solid #1b1f2326;
	font-size: 0.9rem;
	font-weight: 500;
	padding: 0.3em 1em;
	background: transparent;
	color: var(--color-text-primary);
}

.profile__info .social__metrics {
	color: var(--color-text-secondary);
	margin: 1em 0;
	font-size: 0.9rem;
	display: flex;
	align-items: center;
}

.social__metrics svg {
	vertical-align: text-bottom;
	fill: var(--color-text-secondary);
}

.social__metrics span > span {
	color: var(--color-text-primary);
	font-weight: 600;
}

.meta__list {
	display: none;
}

/* REPO TABS SECTION */
.tabs {
	border-bottom: 1px solid var(--border-color);
	display: grid;
	grid-template-columns: 32% 1fr;
	margin-top: 0.3em;
	position: sticky;
	top: 0;
	background: #fff;
	padding-top: 0.8em;
	z-index: 2;
}

.tab__list {
	display: flex;
	align-items: center;
	overflow: auto;
	grid-column: 1/3;
}

.tab__list svg {
	fill: #959da5;
}

.tab__list span {
	margin-left: 0.3em;
	font-size: 0.9rem;
}

.tab__list .repos {
	border-bottom: 2px solid #f9826c;
	color: var(--color-text-primary);
	font-weight: 500;
}

.tab__list .repos svg {
	fill: var(--color-text-primary);
}

.tab__list .repos .counter {
	display: inline-block;
	padding: 0 6px;
	font-size: 0.78rem;
	font-weight: 500;
	line-height: 1.5;
	background-color: var(--tab-counter-color);
	border: 1px solid transparent;
	border-radius: 2em;
	margin-left: 0.7em;
}

/* Hide scrollbar for Chrome, Safari and Opera */
.tab__list::-webkit-scrollbar {
	display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.tab__list {
	-ms-overflow-style: none; /* IE and Edge */
	scrollbar-width: none; /* Firefox */
}

.tab {
	padding-left: 1em;
	padding-right: 1em;
	padding-bottom: 0.7em;
	display: flex;
	align-items: center;
	cursor: pointer;
	color: var(--color-text-primary);
	border-bottom: 2px solid transparent;
}
.tab:last-child {
	margin-right: 0;
}

.tab:not(:nth-child(2)):hover {
	border-color: #d1d5da;
}

.tab__icons {
	display: none;
}

@media (min-width: 540px) {
	.tab__icons {
		display: block;
	}
}

.temp__container {
	position: relative;
	display: none;
}

.temp__info {
	display: none;
	align-items: center;
	padding: 0 1em;
	position: absolute;
	right: 21%;
	top: -13%;
}

.temp__info .temp__thumbnail {
	width: 33px;
	border-radius: 50%;
}

.temp__info .temp__username {
	margin-left: 0.5em;
}

.temp__open {
	display: flex;
}

.repos__content {
	padding-right: 1em;
	padding-left: 1em;
	max-width: 59em;
}
.repos__content .repos__form {
	padding-bottom: 1em;
	border-bottom: 1px solid var(--border-color);
	display: grid;
	grid-template-columns: 1fr;
	grid-template-rows: auto auto;
	grid-gap: 1em;
}

.repos__form .repos__buttons {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.repos__buttons .filter__buttons {
	margin-right: 1em;
}

.repos__buttons .repos__btn {
	color: var(--color-text-primary);
	background-color: #fafbfc;
	box-shadow: 0 1px 0 rgba(27, 31, 35, 0.04), inset 0 1px 0 hsla(0, 0%, 100%, 0.25);
	border: 1px solid #1b1f2326;
	font-size: 0.9rem;
	font-weight: 500;
	padding: 0.4em 1em;
	white-space: nowrap;
}

.repos__buttons .repos__btn:first-child {
	margin-right: 0.3em;
}

.repos__buttons .new__btn {
	background-color: #2ea44f;
	color: #fff;
}

.repos__buttons .new__btn svg {
	fill: #fff;
}

.repos__btn span {
	opacity: 0.75;
}

.repos__btn svg {
	vertical-align: text-bottom;
	opacity: 0.75;
}

.search__form {
	flex: 1;
}

.search__form .search__input {
	width: 100%;
	border: 1px solid var(--border-color);
	border-radius: 6px;
	padding: 0.4em 0.8em;
	font-size: 0.9rem;
}

.repos{
	margin-top: 1em;
}

/* REPOSITORY COMPONENT- START */
.repo__row {
	padding: 1em 0;
	display: flex;
	justify-content: space-between;
	border-bottom: 1px solid var(--border-color) !important;
	overflow: auto;
}
.repo__row:last-child {
	border-bottom: none;
}

.left__content {
	color: var(--color-text-secondary);
	max-width: 35em;
}

.top__row {
	position: relative;
	display: flex;
	align-items: center;
	margin-bottom: 0.7em;
}

.left__content .name {
	color: var(--link-color);
	font-size: 1.37rem;
	font-weight: 600;
	display: inline-block;
}
.left__content .name:hover {
	text-decoration: underline;
}

.left__content .extra {
	display: inline-block;
	border: 1px solid var(--border-color);
	color: var(--color-text-secondary);
	padding: 0 0.5em;
	font-size: 0.75rem;
	font-weight: 500;
	line-height: 1.5;
	border-radius: 2em;
	margin-left: 1em;
}

.left__content .desc {
	margin-bottom: 1em;
	font-size: 0.9rem;
	overflow: hidden;
	text-overflow: ellipsis;
	display: -webkit-box;
	-webkit-line-clamp: 3;
	-webkit-box-orient: vertical;
}

.left__content .bottom__row {
	font-size: 0.8rem;
	line-height: 1.8;
}

.bottom__row .item {
	margin-right: 1em;
}
.bottom__row .item:last-child {
	margin-right: 0;
	white-space: nowrap;
}

.bottom__row .item svg {
	fill: #6a737d;
	vertical-align: text-bottom;
}

.bottom__row .language {
	position: relative;
	top: 1px;
	display: inline-block;
	width: 12px;
	height: 12px;
	border-radius: 50%;
}

.right__content .star {
	color: var(--color-text-primary);
	background-color: #fafbfc;
	border: 1px solid #1b1f2326;
	border-radius: 6px;
	font-weight: 500;
	font-size: 0.8rem;
	padding: 0.5em 1em;
	display: flex;
	box-shadow: 0 1px 0 rgba(27, 31, 35, 0.04), inset 0 1px 0 hsla(0, 0%, 100%, 0.25);
}

.star svg {
	fill: #6a737d;
}

.star span {
	margin-left: 0.3em;
}
/* REPOSITORY COMPONENT- END */

.error {
	text-align: center;
	color: #c54e65;
	font-weight: 500;
	font-size: 1.3rem;
}

@media (min-width: 868px) {
	.main {
		grid-template-columns: 32% 1fr;
	}

	.tabs {
		order: -1;
		grid-column: 1/3;
		grid-gap: 1em;
	}

	.temp__container {
		display: block;
	}

	/* .tab__list {
		grid-column: 2/3;
	} */

	.profile__info {
		top: -3em;
		max-width: 20em;
		margin-left: auto;
	}

	.profile__info .avatar {
		width: 100%;
		z-index: 3;
		margin-right: 0;
	}

	.profile__info .metadata {
		margin-left: 0;
		margin-top: 0.5em;
	}

	.profile__info .dart {
		display: flex;
		align-items: baseline;
	}

	.dart:hover {
		box-shadow: 0 0 20px #4d4d4d1a;
	}

	.dart:hover .status__message {
		display: inline-block;
		color: var(--link-color);
	}

	.meta__list {
		display: block;
		margin-top: 2em;
	}

	.meta__list .meta__info {
		font-size: 0.9rem;
		margin-bottom: 0.4em;
	}

	.meta__list svg {
		width: 1em;
		margin-right: 0.3em;
		vertical-align: text-bottom;
	}

	.repos .repos__content {
		padding-left: 0;
	}

	.repos__content .repos__form {
		grid-template-columns: 1fr auto;
	}

	.repos__form .repos__buttons {
		justify-content: stretch;
	}
}

</style>
