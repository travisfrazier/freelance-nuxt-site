<template>
	<section class="projects__section">
		<div class="projects__top">
			<h2>Recent Work</h2>
			<a href="#contact">
				<button>Contact Me</button>
			</a>
		</div>
		<div class="projects__container">
			<div
				v-bind:key="project.id"
				v-for="project in projects"
				class="projects__item"
			>
				<div
					class="project__item--img"
					:style="{
						'background-image':
							'url(' + `/images/${project.img}` + ')',
					}"
				>
					<div class="projects__overlay">
						<a v-bind:href="project.live">
							<button>View Project</button>
						</a>
					</div>
				</div>
				<h3>{{ project.name }}</h3>
				<div class="projects__item--skills">
					<p>{{ project.skillOne }}</p>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			projects: [
				{	
					img: 'yoga-fuzn.png',
					name: 'Yoga Fuzn',
					skillOne: 'SquareSpace site build',
					live: 'https://yogafuzn.com',
					id: 1,
				},
				{
					img: 'space-tourism.png',
					name: 'Space Travel Website',
					skillOne: 'Custom site build',
					live: 'https://space-tourism-vuejs.netlify.app',
					id: 2,
				},
				{
					img: 'bench-clearers.png',
					name: 'Bench Clearers Shopify',
					skillOne: 'Custom Shopify development',
					live: 'https://benchclearers.com',
					id: 3,
				},
				{
					img: 'sandy-vans.png',
					name: 'Sandy Vans',
					skillOne: 'Custom data marketing integrations',
					live: 'https://themimosasnailbar.com/',
					id: 4,
				},
				{
					img: 'another-salon.png',
					name: 'Another Salon Studio',
					skillOne: 'Squarespace site work',
					live: 'https://www.anothersalon.com/',
					id: 5,
				},
				{
					img: 'yogiroll.png',
					name: 'YogiRoll',
					skillOne: 'Shopify site build',
					live: 'https://yogiroll.com',
					id: 6,
				},
				{
					img: 'natalie-lmft.png',
					name: 'Natalie Coates',
					skillOne: 'Squarespace site build',
					live: 'https://www.nataliecoateslmft.com/',
					id: 7,
				},
				{
					img: 'mimosas.png',
					name: 'Mimosas Nails',
					skillOne: 'Custom site build',
					live: 'https://themimosasnailbar.com/',
					id: 8,
				}
			],
		};
	},
	methods: {
		animateProjects() {
			gsap.set('.projects__item', {
				opacity: 0,
			});

			gsap.to('.projects__item', {
				opacity: 1,
				duration: 2.5,
				stagger: 1,
				scrollTrigger: {
					trigger: '.projects__container',
					scrub: 0.5,
				},
			});
		},
	},
	// mounted() {
	// 	this.animateProjects();
	// },
};
</script>

<style lang="scss" scoped>
.projects__section {
	padding-bottom: 100px;
}

.projects__top {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 80px;
	padding-top: 20px;
}

h2 {
	@include font-xl;
}

h3 {
	@include font-m;
	text-transform: uppercase;
	margin-bottom: 12px;
}

.projects__container {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(450px, 1fr));
	gap: 20px;
	@media only screen and (max-width: $mobile) {
		grid-template-columns: 1fr;
		gap: 30px;
	}
}

.project__item--img {
	height: 400px;
	background-position: center;
	background-size: cover;
	margin-bottom: 20px;
	position: relative;

	@media only screen and (max-width: $mobile) {
		height: 275px;
	}

	&:hover {
		.projects__overlay {
			opacity: 1;
			visibility: visible;
		}
	}

	.projects__overlay {
		visibility: hidden;
		opacity: 0;
		transition: opacity 500ms ease-in-out, visibility 500ms ease-in-out 0ms;
		position: absolute;
		width: 100%;
		height: 100%;
		background-color: #25252598;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 20px;
	}
}

.projects__item--skills {
	display: flex;
	gap: 10px;
	text-transform: uppercase;
}
</style>
