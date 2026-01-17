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

</script>

<h2>Frutería</h2>

{#each productos as producto}
	<button>
		{producto.nombre}
	</button>
{/each}


<h3>Ticket</h3>
<ul>
	{#each ticket as producto, i}
		<li>
			{producto.nombre} - {producto.precio} €
			<button>
				Eliminar
			</button>
		</li>
	{/each}
</ul>

<p><strong>Total:</strong> {total}</p>