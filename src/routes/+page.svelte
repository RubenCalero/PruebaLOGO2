<script>
	let productos = [
		{ nombre: 'Manzana', precio: 1.5 },
		{ nombre: 'Pera', precio: 1.2 },
		{ nombre: 'Plátano', precio: 0.8 },
		{ nombre: 'Uva', precio: 2.5 },
		{ nombre: 'Naranja', precio: 1.0 }
	];

	let ticket = [];
	let total = 0;

	function agregarAlTicket(producto) {
		ticket.push(producto);
		ticket = ticket;
				
        let suma = 0;
		for (let i = 0; i < ticket.length; i = i + 1) {
			suma = suma + ticket[i].precio;
		}
		total = suma;
	}

	function eliminarDelTicket(indice) {
		ticket.splice(indice, 1);
		ticket = ticket;
		
		let suma = 0;
		for (let i = 0; i < ticket.length; i = i + 1) {
			suma = suma + ticket[i].precio;
		}
		total = suma;
	}

</script>

<h2>Frutería</h2>

{#each productos as producto}
	<button on:click={function() { agregarAlTicket(producto) }}>
		{producto.nombre}
	</button>
{/each}

<hr />

<h3>Ticket</h3>
<ul>
	{#each ticket as producto, i}
		<li>
			{producto.nombre} - {producto.precio} €
			<button on:click={function() { eliminarDelTicket(i) }}>
				Eliminar
			</button>
		</li>
	{/each}
</ul>

<p><strong>Total:</strong> {total}</p>