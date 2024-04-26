<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';
	import '$css/themes.css';
	import '$css/css.css';
	const themes = [
		'This_Automatic_Eden',
		'Neon_Nights',
		'josan-gonzales',
		'aoihana6',
		'bg-palmtrees',
		'bg-retrowallpaper',
		'masashi-wakui-101',
		'masashi-wakui-102',
		'masashi-wakui-103',
		'masashi-wakui-104',
		'masashi-wakui-105'
	];
	const fonts = ['Argon', 'Neon', 'Xenon'];
	const randoTheme = themes[Math.floor(Math.random() * themes.length)];
	const randoFont = fonts[Math.floor(Math.random() * fonts.length)];
	onMount(async () => {
		await import('$lib/theme-selector');
	});
</script>

<div class="bg"></div>
<main style="--rando-font: {randoFont}">
	<article>
		<section class="title-section">
			<div class="title-text">
				<h4 class="title-top">a little</h4>
				<h3 class="title">Portfolio</h3>
				<h4 class="title-bottom">by</h4>
				<h1 class="name">Nick White</h1>
			</div>
		</section>
		<section class="body-text">
			<p>
				While my resume has these links as well, I wanted to take the opportunity to provide context
				for the projects.
			</p>
			<div class="halloween">
				<h2>Halloween</h2>
				<p>
					For Halloween, I invented a whole mascot for the library. I did not ask permission. ...But
					I'm not entirely sure anyone knows he's our mascot. His name is Enzo -- or maybe Nzo.
				</p>
				<a href="https://digital.newberry.org/collection-stories/halloween/" target="_blank">
					<img src="{base}/images/s-halloween.webp" alt="" />
				</a>
			</div>
			<div class="winter">
				<h2>Winter</h2>
				<p>
					I did a similar project for the winter -- similar layout, but with a different approach to
					how to delight the user. The snow consists of a number of different css animations
					alternating speed and scale to give each a unique look. See if you can find Nzo!
				</p>
				<a href="https://digital.newberry.org/collection-stories/winter/" target="_blank">
					<img src="{base}/images/s-winter.webp" alt="" />
				</a>
			</div>
			<div class="mapmov">
				<h2>Mapping Movement</h2>
				<p>
					Mapping Movement was a 15-year-old academic "online book" which I was asked to revitalize.
					I wasn't eager, at first, to take on someone else's vision -- but the result is one of the
					projects of which I'm the most proud -- while the design language doesn't feel like mine,
					the way I was able to incorporate the concept and content of the project into the design
					makes it among my favorites.
				</p>
				<a href="https://mappingmovement.newberry.org/" target="_blank">
					<img src="{base}/images/s-mapmov.webp" alt="" />
				</a>
			</div>
			<div class="wip">
				<h2>Works in Progress</h2>
				<h3>Royko</h3>
				<p>
					A couple of works-in-progress: the `Royko` project is... very close to complete. It's very
					simple -- it's an in-gallery interactive to present a handful of articles written by the
					exhibit's subject, Mike Royko. Between the animated background and how I handled the text
					of the articles, there's a lot that I like about it, despite how simple it is. I'll save
					the details of what's so important about those details for a conversation!
				</p>
				<a href="https://digital.newberry.org/royko/" target="_blank">
					<img src="{base}/images/s-royko.webp" alt="" />
				</a>

				<h3>Transcrib3</h3>
				<p>
					And finally, something I'm both very excited about, but also very far from completing: a
					rebuild of our Newberry Transcribe project. It's built in Svelte then ported to PHP to be
					interwoven with the COTS software Omeka. The reason I'm sharing it is because of the home
					page's splash. I'm quite proud of what I was able to accomplish with the layering to solve
					the problem of handling title text transitioning from a dark background to a light one --
					so make sure you scroll down. (As I said, it's far from finished, but that part is solid.)
				</p>
				<a href="http://transcribe.newberry.org/ohmekas/s/transcribe/page/home" target="_blank">
					<img src="{base}/images/s-transcrib3.webp" alt="" />
				</a>
			</div>
			<div class="bonus">
				<h2>Bonus Content for Scrollers</h2>
				<p>
					Some debate is currently going on about the darkness of the tint over some of the splash
					in the transcribe project, so I made this tool for my colleagues to play with the levels
					to find something they like.
				</p>
				<a href="https://nick3white.github.io/opacity-contrast-checker/" target="_blank">
					<img src="{base}/images/s-opacity.webp" alt="" />
				</a>
			</div>
		</section>
	</article>
</main>

<theme-selector {themes} defaultTheme={randoTheme}></theme-selector>

<style>
	main {
		color: rgb(var(--foreground));
		display: flex;
		flex-direction: column;
		justify-content: start;
		align-items: center;
		font-family: var(--rando-font);
		position: relative;
		backdrop-filter: blur(10px);
	}
	.bg {
		background-image: var(--wallpaper);
		background-size: cover;
		background-position: center;
		z-index: 0;
		content: '';
		position: fixed;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
	}
	article, .title-section {
	background-image: var(--wallpaper);
	background-position: center;
	background-size: cover;
	background-attachment: fixed;

	}
	article {

		padding-block: 22rem;

		width: min(555px, 90vw);
	}
	.body-text,
	.title-text {
		background: rgba(var(--background), 0.87);
		backdrop-filter: blur(10px) saturate(3.3);
	}
	.title-section {
		height: 22rem;
		// padding-block: 3rem;
		position: sticky;
		top: -11rem;
		z-index: 10;
	}
	.title-text {
		position: sticky;
		top: -1rem;
		padding: 0 2rem 1rem 2rem;
		margin: 0;
		& .title-top,
		.title,
		.title-bottom,
		.name {
			margin-block: 0;
		}
		.title-top {
			margin-inline: 2rem;
		}
		.title-bottom {
			margin-inline: 3rem;
		}
		.title {
			margin-inline: 1rem;
		}
	}
	.name,
	.title {
		position: sticky;
	}
	.name {
		margin-bottom: 10px !important;
		top: 3rem;
		font-size: clamp(1.25rem, -0.2875rem + 6.8333vw, 3.3rem);
	}
	.title {
		top: 7rem;
		font-size: clamp(1rem, 0.625rem + 1.6667vw, 1.5rem);
	}
	.body-text {

	}
	h2, .body-text h3 {
	position: sticky;
	padding-inline: 2rem;
	background: rgba(var(--color7));
	color: rgba(var(--color0));

	}
	h2 {

	top: 11rem;
	}
	.body-text h3 {

	top: 13rem;
	}
	p  {
	padding-inline: 2rem;
	}
	p {
		margin: 0;
		padding: 1rem 2rem;
		font-size: 1.1rem;
		line-height: 2rem;
	}
	img
 { width: 100%;

 padding-inline: 2rem;
		object-fit: contain;

	}
	img {
		margin-bottom: 33px;
	}
</style>
