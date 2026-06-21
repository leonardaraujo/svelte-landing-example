<svelte:head>
	<title>Abogado Martinez | Asesoria Legal</title>
	<meta
		name="description"
		content="Asesoria legal clara y cercana para familias, trabajadores y pequenos negocios."
	/>
</svelte:head>

<main class="min-h-screen bg-stone-950 text-stone-100">
	<section class="mx-auto flex min-h-screen w-full max-w-6xl flex-col px-6 py-6">
		<header class="flex items-center justify-between border-b border-white/10 pb-5">
			<a href="/" class="text-lg font-semibold tracking-wide">Martinez Legal</a>

			<a
				href="https://wa.me/5215555555555"
				class="rounded-full border border-amber-300/40 px-4 py-2 text-sm font-medium text-amber-200 transition hover:bg-amber-300 hover:text-stone-950"
			>
				WhatsApp
			</a>
		</header>

		<div class="grid flex-1 items-center gap-12 py-16 md:grid-cols-[1.15fr_0.85fr]">
			<div>
				<p class="mb-4 text-sm font-semibold uppercase tracking-[0.35em] text-amber-300">
					Derecho civil y familiar
				</p>

				<h1 class="max-w-3xl text-5xl font-bold leading-tight text-white md:text-7xl">
					Asesoria legal clara para tomar buenas decisiones.
				</h1>

				<p class="mt-6 max-w-2xl text-lg leading-8 text-stone-300">
					Acompanamiento profesional en contratos, divorcios, sucesiones, pensiones y conflictos
					legales. Atencion personalizada desde la primera consulta.
				</p>

				<div class="mt-9 flex flex-col gap-3 sm:flex-row">
					<a
						href="https://wa.me/5215555555555?text=Hola,%20quiero%20agendar%20una%20consulta%20legal"
						class="rounded-full bg-amber-300 px-6 py-3 text-center font-semibold text-stone-950 transition hover:bg-amber-200"
					>
						Agendar consulta
					</a>

					<a
						href="#servicios"
						class="rounded-full border border-white/15 px-6 py-3 text-center font-semibold text-white transition hover:border-white/40"
					>
						Ver servicios
					</a>
				</div>
			</div>

			<aside class="rounded-3xl border border-white/10 bg-white/[0.04] p-6 shadow-2xl shadow-black/40">
				<div class="rounded-2xl bg-stone-900 p-6">
					<p class="text-sm uppercase tracking-[0.25em] text-amber-300">Consulta inicial</p>
					<h2 class="mt-4 text-3xl font-bold text-white">Respuesta en menos de 24 horas</h2>
					<p class="mt-4 leading-7 text-stone-300">
						Explica tu caso por WhatsApp y recibe orientacion sobre los siguientes pasos.
					</p>

					<div class="mt-8 space-y-4 text-sm text-stone-200">
						<p class="rounded-xl bg-white/[0.05] p-4">Honorarios claros desde el inicio</p>
						<p class="rounded-xl bg-white/[0.05] p-4">Atencion presencial y en linea</p>
						<p class="rounded-xl bg-white/[0.05] p-4">Trato directo con el abogado</p>
					</div>
				</div>
			</aside>
		</div>
	</section>

	<section id="servicios" class="border-t border-white/10 bg-stone-900 px-6 py-16">
		<div class="mx-auto grid max-w-6xl gap-5 md:grid-cols-3">
			<div class="rounded-2xl border border-white/10 bg-stone-950 p-6">
				<h3 class="text-xl font-semibold text-white">Derecho familiar</h3>
				<p class="mt-3 text-stone-300">Divorcios, pensiones alimenticias, convenios y custodia.</p>
			</div>

			<div class="rounded-2xl border border-white/10 bg-stone-950 p-6">
				<h3 class="text-xl font-semibold text-white">Contratos</h3>
				<p class="mt-3 text-stone-300">Revision y elaboracion de contratos civiles y comerciales.</p>
			</div>

			<div class="rounded-2xl border border-white/10 bg-stone-950 p-6">
				<h3 class="text-xl font-semibold text-white">Sucesiones</h3>
				<p class="mt-3 text-stone-300">Testamentos, herencias y regularizacion de bienes familiares.</p>
			</div>
		</div>
	</section>
</main>
