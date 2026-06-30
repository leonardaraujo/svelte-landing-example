<script lang="ts">
	const whatsappUrl = 'https://wa.me/51940941857';

	let nombre = $state('');
	let telefono = $state('');
	let tipo = $state('Seleccione una especialidad');
	let mensaje = $state('');

	function handleSubmit(event: Event) {
		event.preventDefault();
		const texto = `Hola, soy ${nombre || '---'}.%0ATelefono: ${telefono || '---'}%0AConsulta: ${tipo}%0AMensaje: ${mensaje || '---'}`;
		window.open(`${whatsappUrl}?text=${texto}`, '_blank');
	}

	const trustItems = ['Atencion confidencial', 'Respuesta rapida', 'Asesoria personalizada'];

	const services = [
		{
			icon: 'balance',
			title: 'Derecho familiar',
			description: 'Divorcios, pensiones, custodia y sucesiones con un enfoque empatico y firme.',
			featured: true
		},
		{
			icon: 'description',
			title: 'Derecho civil',
			description: 'Resolucion de conflictos, propiedad, indemnizaciones y responsabilidad civil.'
		},
		{
			icon: 'work',
			title: 'Derecho laboral',
			description: 'Despidos, beneficios sociales y asesoria para trabajadores y empresas.'
		},
		{
			icon: 'history_edu',
			title: 'Contratos y documentos',
			description: 'Redaccion, revision y negociacion de acuerdos legales seguros.',
			featured: true
		},
		{
			icon: 'business',
			title: 'Asesoria empresarial',
			description: 'Constitucion de empresas, cumplimiento normativo y asesoria corporativa continua.'
		},
		{
			icon: 'shield',
			title: 'Defensa legal',
			description: 'Representacion solida en litigios para proteger sus intereses ante tribunales.'
		}
	];

	const reasons = [
		{
			icon: 'verified',
			title: 'Atencion clara',
			description: 'Explicamos su situacion legal sin tecnicismos innecesarios.'
		},
		{
			icon: 'lock',
			title: 'Confidencialidad absoluta',
			description: 'Sus datos y su caso son tratados con el mas estricto secreto profesional.'
		},
		{
			icon: 'balance',
			title: 'Compromiso etico',
			description: 'Buscamos siempre la solucion legal mas conveniente para usted.'
		}
	];
</script>

<svelte:head>
	<title>Justitia Law | Asesoria Legal Confiable</title>
	<meta
		name="description"
		content="Asesoria legal confiable en derecho familiar, civil, laboral y empresarial. Agenda una consulta por WhatsApp."
	/>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&family=Playfair+Display:wght@600;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<main class="min-h-screen bg-[#f7fafc] font-['Inter'] text-[#181c1e] antialiased">
	<header class="fixed inset-x-0 top-0 z-50 border-b border-[#c5c6ce] bg-[#f7fafc]/95 shadow-sm backdrop-blur">
		<div class="mx-auto flex h-20 max-w-[1200px] items-center justify-between px-5 lg:px-10">
			<a href="#inicio" class="flex items-center gap-2 text-[#031632]">
				<span class="material-symbols-outlined text-3xl">gavel</span>
				<span class="font-['Playfair_Display'] text-2xl font-semibold tracking-tight">JUSTITIA LAW</span>
			</a>

			<nav class="hidden items-center gap-8 text-sm font-semibold tracking-[0.05em] md:flex">
				<a class="border-b-2 border-[#775a19] pb-1 text-[#775a19]" href="#inicio">Inicio</a>
				<a class="pb-1 text-[#031632] transition hover:text-[#775a19]" href="#servicios">Servicios</a>
				<a class="pb-1 text-[#031632] transition hover:text-[#775a19]" href="#contacto">Contacto</a>
			</nav>
		</div>
	</header>

	<section id="inicio" class="pt-20">
		<div class="mx-auto grid min-h-[calc(100vh-80px)] max-w-[1200px] items-center gap-12 px-5 py-16 lg:grid-cols-[0.8fr_1.2fr] lg:px-10 lg:py-28">
			<div class="max-w-2xl">
				<div class="mb-4 flex items-center gap-3">
					<div class="h-px w-10 bg-[#775a19]"></div>
					<p class="text-sm font-semibold uppercase tracking-[0.25em] text-[#775a19]">Estudio legal independiente</p>
				</div>

				<h1 class="font-['Playfair_Display'] text-4xl font-bold leading-tight tracking-tight text-[#031632] sm:text-5xl lg:text-6xl">
					Asesoria legal confiable para proteger tus derechos
				</h1>

				<p class="mt-6 max-w-xl text-lg leading-8 text-[#44474d]">
					Atencion personalizada en casos familiares, civiles, laborales y empresariales. Soluciones claras y efectivas para su tranquilidad.
				</p>

				<div class="mt-10 flex flex-col gap-4 sm:flex-row">
					<a
						href={whatsappUrl}
						class="inline-flex items-center justify-center gap-2 rounded bg-[#25d366] px-8 py-4 text-sm font-semibold uppercase tracking-[0.05em] text-white transition hover:-translate-y-0.5 hover:bg-[#1ebe57] hover:shadow-xl"
					>
						<img src="/wsp.svg" alt="WhatsApp" class="h-6 w-6" />
						Consultar por WhatsApp
					</a>
					<a
						href="#servicios"
						class="inline-flex items-center justify-center rounded border border-[#775a19] px-8 py-4 text-sm font-semibold uppercase tracking-[0.05em] text-[#775a19] transition hover:bg-[#775a19] hover:text-white"
					>
						Ver servicios
					</a>
				</div>

				<div class="mt-10 flex flex-wrap gap-6 border-t border-[#c5c6ce] pt-5">
					{#each trustItems as item}
						<div class="flex items-center gap-2 text-sm text-[#44474d]">
							<span class="material-symbols-outlined text-base text-[#775a19]">check_circle</span>
							<span>{item}</span>
						</div>
					{/each}
				</div>
			</div>

			<div class="relative hidden lg:block">
				<div class="relative aspect-[1.3] overflow-hidden rounded-2xl border border-[#c5c6ce]/30 shadow-[0_32px_64px_rgba(3,22,50,0.15)]">
					<img
						src="/main_image.webp"
						alt="Oficina legal elegante"
						class="h-full w-full object-cover"
					/>
					<div class="absolute inset-0 bg-gradient-to-t from-[#031632]/20 to-transparent"></div>
				</div>
				<div class="absolute -bottom-4 -right-4 -z-10 h-28 w-28 rounded-xl border border-[#c5c6ce]/20 bg-[#f1f4f6]"></div>
				<div class="absolute -left-4 -top-4 -z-10 h-24 w-24 rounded-xl bg-[#775a19]/5"></div>
			</div>
		</div>
	</section>

	<section id="servicios" class="bg-[#f1f4f6] px-5 py-16 lg:px-10 lg:py-28">
		<div class="mx-auto max-w-[1200px]">
			<div class="mx-auto mb-14 max-w-2xl text-center">
				<h2 class="font-['Playfair_Display'] text-4xl font-semibold text-[#031632]">Servicios legales</h2>
				<p class="mt-4 leading-7 text-[#44474d]">Agenda una consulta y recibe orientacion segun tu caso. Especialidades adaptadas a sus necesidades especificas.</p>
				<div class="mx-auto mt-6 h-1 w-16 bg-[#775a19]"></div>
			</div>

			<div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
				{#each services as service}
					<article class="rounded-lg border border-[#c5c6ce]/40 bg-white p-8 shadow-[0_18px_42px_rgba(3,22,50,0.05)] transition hover:-translate-y-1 {service.featured ? 'border-t-4 border-t-[#775a19]' : ''}">
						<div class="mb-6 flex h-12 w-12 items-center justify-center rounded-full bg-[#f1f4f6] text-[#775a19]">
							<span class="material-symbols-outlined text-2xl">{service.icon}</span>
						</div>
						<h3 class="font-['Playfair_Display'] text-2xl font-semibold text-[#031632]">{service.title}</h3>
						<p class="mt-3 text-sm leading-6 text-[#44474d]">{service.description}</p>
					</article>
				{/each}
			</div>
		</div>
	</section>

	<section id="contacto" class="px-5 py-16 lg:px-10 lg:py-28">
		<div class="mx-auto grid max-w-[1200px] gap-14 lg:grid-cols-2">
			<div>
				<h2 class="font-['Playfair_Display'] text-4xl font-semibold text-[#031632]">Agenda una consulta legal</h2>
				<ul class="mt-8 space-y-5">
					{#each reasons as reason}
						<li class="flex gap-4">
							<span class="material-symbols-outlined mt-1 text-[#775a19]">{reason.icon}</span>
							<div>
								<h3 class="text-sm font-semibold uppercase tracking-[0.05em] text-[#031632]">{reason.title}</h3>
								<p class="mt-1 text-sm leading-6 text-[#44474d]">{reason.description}</p>
							</div>
						</li>
					{/each}
				</ul>

				<div class="mt-10 border-t border-[#775a19] pt-8">
					<h3 class="font-['Playfair_Display'] text-2xl font-semibold text-[#031632]">Informacion de contacto</h3>
					<div class="mt-5 space-y-4">
						<p class="flex items-center gap-3 text-[#44474d]"><span class="material-symbols-outlined text-[#031632]">call</span>+51 940 941 857</p>
						<p class="flex items-center gap-3 text-[#44474d]"><span class="material-symbols-outlined text-[#031632]">schedule</span>Lun - Vie: 9:00 AM - 6:00 PM</p>
						<p class="flex items-center gap-3 text-[#44474d]"><span class="material-symbols-outlined text-[#031632]">location_on</span>Centro de Huancayo, Junin, Peru</p>
					</div>
				</div>
			</div>

			<div class="rounded-xl bg-[#f1f4f6] p-6 shadow-[0_24px_60px_rgba(3,22,50,0.08)] md:p-8">
				<h3 class="font-['Playfair_Display'] text-2xl font-semibold text-[#031632]">Solicitar informacion</h3>
				<form class="mt-6 space-y-4" onsubmit={handleSubmit}>
					<label class="block text-sm font-semibold uppercase tracking-[0.05em] text-[#031632]" for="nombre">Nombre completo</label>
					<input id="nombre" bind:value={nombre} class="w-full rounded border-0 bg-white px-4 py-3 text-[#181c1e] outline-none ring-1 ring-transparent transition focus:ring-[#031632]" placeholder="Ej. Juan Perez" type="text" />

					<label class="block text-sm font-semibold uppercase tracking-[0.05em] text-[#031632]" for="telefono">Telefono</label>
					<input id="telefono" bind:value={telefono} class="w-full rounded border-0 bg-white px-4 py-3 text-[#181c1e] outline-none ring-1 ring-transparent transition focus:ring-[#031632]" placeholder="+51 ..." type="tel" />

					<label class="block text-sm font-semibold uppercase tracking-[0.05em] text-[#031632]" for="tipo">Tipo de consulta</label>
					<select id="tipo" bind:value={tipo} class="w-full rounded border-0 bg-white px-4 py-3 text-[#44474d] outline-none ring-1 ring-transparent transition focus:ring-[#031632]">
						<option>Seleccione una especialidad</option>
						<option>Derecho familiar</option>
						<option>Derecho civil</option>
						<option>Derecho laboral</option>
						<option>Otro</option>
					</select>

					<label class="block text-sm font-semibold uppercase tracking-[0.05em] text-[#031632]" for="mensaje">Mensaje breve</label>
					<textarea id="mensaje" bind:value={mensaje} class="w-full resize-none rounded border-0 bg-white px-4 py-3 text-[#181c1e] outline-none ring-1 ring-transparent transition focus:ring-[#031632]" placeholder="Describa brevemente su caso..." rows="4"></textarea>

					<button type="submit" class="flex w-full items-center justify-center gap-2 rounded bg-[#031632] px-6 py-4 text-sm font-semibold uppercase tracking-[0.05em] text-white transition hover:bg-[#1a2b48]">
						<span class="material-symbols-outlined text-lg">arrow_forward</span>
						Enviar solicitud
					</button>
					<p class="text-center text-xs leading-5 text-[#44474d]">Tus datos estan seguros y seran tratados con confidencialidad.</p>
				</form>
			</div>
		</div>
	</section>

	<section class="bg-[#f7fafc] px-5 py-16 lg:px-10 lg:py-20">
		<div class="mx-auto max-w-[1200px]">
			<div class="mx-auto mb-10 max-w-2xl text-center">
				<h2 class="font-['Playfair_Display'] text-4xl font-semibold text-[#031632]">Ubicanos</h2>
				<p class="mt-4 leading-7 text-[#44474d]">Estamos en el centro de Huancayo. Visitanos o escribenos por WhatsApp.</p>
				<div class="mx-auto mt-6 h-1 w-16 bg-[#775a19]"></div>
			</div>
			<div class="mx-auto overflow-hidden rounded-xl shadow-[0_24px_60px_rgba(3,22,50,0.1)]">
				<iframe
					src="https://www.google.com/maps?q=Huancayo+Junin+Peru+centro&output=embed"
					width="100%"
					height="400"
					style="border:0;display:block"
					allowfullscreen
					loading="lazy"
					referrerpolicy="no-referrer-when-downgrade"
					title="Ubicacion de Justitia Law en Huancayo"
				></iframe>
			</div>
			<div class="mt-6 text-center">
				<a
					href="https://www.google.com/maps?q=Huancayo+Junin+Peru"
					target="_blank"
					rel="noopener noreferrer"
					class="inline-flex items-center gap-2 text-sm font-semibold text-[#775a19] transition hover:text-[#a37a2e]"
				>
					<span class="material-symbols-outlined text-base">open_in_new</span>
					Abrir en Google Maps
				</a>
			</div>
		</div>
	</section>

	<footer class="bg-[#031632] px-5 py-10 text-white lg:px-10">
		<div class="mx-auto flex max-w-[1200px] flex-col items-center justify-between gap-4 text-center md:flex-row md:text-left">
			<div>
				<p class="font-['Playfair_Display'] text-2xl font-semibold">JUSTITIA LAW</p>
				<p class="mt-2 text-xs text-[#8293b5]">© 2026 Estudio Legal. Todos los derechos reservados.</p>
			</div>
			<p class="text-xs text-[#8293b5]">Excelencia legal con integridad.</p>
		</div>
	</footer>

	<a
		href={whatsappUrl}
		aria-label="Contactar por WhatsApp"
		class="fixed bottom-6 right-6 z-50 flex h-14 w-14 items-center justify-center rounded-full bg-[#25d366] text-white shadow-lg transition hover:scale-110 hover:bg-[#1ebe57]"
	>
		<img src="/wsp.svg" alt="WhatsApp" class="h-7 w-7" />
	</a>
</main>
