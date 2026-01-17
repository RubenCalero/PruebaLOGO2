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
    <div>
	<button 
        class="bg-blue-100 hover:bg-blue-200 px-3 py-1 m-1 rounded-md"
        on:click={function() { agregarAlTicket(producto) }}>
		{producto.nombre}
	</button>
    </div>
    
{/each}

<hr />

<h3>Ticket</h3>
<ul>
	{#each ticket as producto, i}
		<li>
			{producto.nombre} - {producto.precio} €
			<button
                class="bg-red-100 hover:bg-red-200 px-3 py-1 m-1 rounded-md"
                on:click={function() { eliminarDelTicket(i) }}>
				Eliminar
			</button>
		</li>
	{/each}
</ul>
<p><strong>Total:</strong> <span class="bg-green-100 px-3 rounded-md">{total}</span></p>