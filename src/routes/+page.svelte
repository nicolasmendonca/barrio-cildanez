<script lang="ts">
	import { onMount } from 'svelte';

	let parallaxContent: HTMLDivElement;

	onMount(() => {
		const scrollHandler = () => {
			const { scrollTop, scrollHeight } = document.scrollingElement!;
			const percentageScrolled = scrollTop / (scrollHeight - window.innerHeight);
			parallaxContent.style.backdropFilter = `blur(${percentageScrolled * 20}px)`;
		};
		window.addEventListener('scroll', scrollHandler);

		return () => {
			window.removeEventListener('scroll', scrollHandler);
		};
	});
</script>

<main class="relative">
	<div class="parallax">
		<div class="w-full h-full bg-black/50" bind:this={parallaxContent}>
			<div class="flex flex-col items-center justify-center w-full h-full">
				<h1
					class="sticky pt-4 top-0 drop-shadow text-balance w-[650px] text-center leading-loose"
				>
					<div class="text-yellow-400 font-extrabold text-xl md:text-4xl">Intervención Estructural</div>
					<div class="text-white font-serif font-semibold text-xl md:text-6xl">Barrio Cildañez</div>
				</h1>
			</div>
		</div>
	</div>

	<div class="max-w-screen-lg mx-auto my-32 flex flex-col md:flex-row items-start gap-24 mx-8">
		<div class="space-y-4 md:w-1/2">
			<p>
				¡Bienvenidos al sitio web de la propuesta de intervención VÍNCULO ENTRE LA CIUDAD FORMAL E
				INFORMAL! En este espacio encontrarás información detallada sobre cómo se busca mejorar el
				ambiente urbano peatonal en el vínculo entre el Barrio Cildañez y su entorno inmediato.
			</p>

			<p>
				Nuestra propuesta tiene como objetivo principal revitalizar el espacio público y potenciar
				el sentido de comunidad en la zona del Anfiteatro Villa Cildañez. Para lograrlo, se han
				establecido tres objetivos específicos: la mejora del ambiente urbano peatonal, el
				incremento de espacios públicos de encuentro social con calidad urbana y el alumbrado
				público adecuado.
			</p>

			<p>
				Para llevar a cabo esta propuesta, se han establecido distintas actividades que se
				ejecutarán en un plazo de 12 semanas. Entre ellas, se encuentra la ejecución de los
				corredores urbanos en base a lo pactado en el contrato y según diseño, la participación en
				talleres, foros y dispositivos de participación ciudadana, y el monitoreo y control del
				proyecto a través de observatorios e indicadores de seguimiento.
			</p>
		</div>
		<div class="space-y-4 md:w-1/2">
			<p>
				La propuesta involucra a distintos actores sociales, entre ellos la Dirección General de
				Regeneración Urbana Estatal/Gubernamental, empresas de publicidad y la Secretaría de Obras
				Públicas, entre otros. Además, cuenta con un financiamiento público y recursos físicos y
				económicos para su ejecución.
			</p>

			<p>
				En este sitio web, podrás encontrar información detallada sobre cada uno de los objetivos
				específicos, las actividades a realizar y los actores sociales involucrados. Además, te
				mantendremos informado sobre el avance del proyecto y los resultados obtenidos.
			</p>

			<p>
				¡Únete a nuestra propuesta de intervención y ayúdanos a mejorar el ambiente urbano peatonal
				en el vínculo entre el Barrio Cildañez y su entorno inmediato!
			</p>
		</div>
	</div>

	<div class="masonry sm:masonry-sm md:masonry-md space-y-8 mb-24">
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/daniel-mccullough-HtBlQdxfG9k-unsplash.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/neal-e-johnson-ddK3u7QVWJQ-unsplash.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/pedro-miranda-3QzMBrvCeyQ-unsplash.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/premium_photo-1673240159028-5f968f12e1c3.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/premium_photo-1688114988405-5849e59e961b.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/ryan-ancill-nGsVMkRatgM-unsplash.webp"
			alt=""
		/>
		<img
			loading="lazy"
			class="rounded-md object-cover"
			src="/images/tom-rumble-7lvzopTxjOU-unsplash.webp"
			alt=""
		/>
	</div>
</main>

<iframe
	title="google map"
	class="w-full max-w-screen-xl h-[75vh] mx-auto my-12"
	src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4997.715198504589!2d-58.475976072975605!3d-34.65924857293443!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x95bcc96673243d69%3A0x3276f0b850fb52cd!2sBarrio%20Cild%C3%A1%C3%B1ez%20-%20Villa%206%2C%20C1407%20Buenos%20Aires!5e1!3m2!1sen!2sar!4v1698896240241!5m2!1sen!2sar"
	style="border:0;"
	allowfullscreen={false}
	loading="lazy"
	referrerpolicy="no-referrer-when-downgrade"
/>

<footer class="w-full h-[300px] bg-yellow-400 px-12 py-12 flex items-center">
	<div class="flex flex-col gap-8">
		<h3 class="font-bold text-xl">Contacto</h3>
		<ul class="space-y-2">
			<li>Cesia Menis</li>
			<li>Brenda Gómez</li>
			<li>Karen Franchelli</li>
			<li>Luz Carrasco</li>
		</ul>
	</div>
</footer>

<style>
	.parallax {
		background-image: url('/images/premium_photo-1673240159028-5f968f12e1c3.webp');
		height: 100vh;
		width: 100vw;
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		background-attachment: fixed;
	}

	.text-balance {
		text-wrap: balance;
	}
</style>
