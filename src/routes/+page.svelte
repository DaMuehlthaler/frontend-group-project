<script>
	let cardholderName = '';
	let cardNumber = '';
	let expiryMonth = '';
	let expiryYear = '';
	let cvc = '';
	let isSubmitted = false;

	$: formattedCardNumber = cardNumber
		.replace(/\D/g, '') // Only digits
		.replace(/(.{4})/g, '$1 ') // Space every 4 digits
		.trim();

	function handleSubmit() {
		isSubmitted = true;
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
	href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300..700&display=swap"
	rel="stylesheet"
/>

<div
	class="h-screen flex flex-col lg:flex-row items-center justify-center bg-gradient-to-b from-violet-900 to-black font-space-grotesk"
>
	{#if !isSubmitted}
		<div
			class="relative flex-1 flex flex-col items-center lg:items-start lg:justify-center lg:ml-[10%]"
		>
			<div
				class="relative w-[280px] lg:w-[400px] h-[160px] lg:h-[220px] bg-gradient-to-r from-purple-600 to-pink-500 rounded-lg p-5 shadow-xl lg:ml-[10%]"
			>
				<div class="flex justify-between items-center">
					<div class="w-10 h-10 bg-white rounded-full"></div>
					<div class="w-5 h-5 border border-white rounded-full"></div>
				</div>
				<p class="mt-6 text-white text-xl lg:text-2xl tracking-widest">
					{formattedCardNumber || '0000 0000 0000 0000'}
				</p>
				<div class="flex justify-between mt-4 text-white text-sm lg:text-base">
					<p>{cardholderName || 'Habl Rans'}</p>
					<p>{expiryMonth || '00'}/{expiryYear || '00'}</p>
				</div>
			</div>
			<div
				class="relative mt-4 w-[280px] lg:w-[400px] h-[160px] lg:h-[220px] bg-gray-800 rounded-lg p-5 shadow-xl lg:ml-[8%]"
			>
				<div class="absolute top-[30%] left-0 right-0 h-[40px] bg-gray-700"></div>
				<p class="absolute bottom-5 right-5 text-white text-sm lg:text-base">{cvc || '123'}</p>
			</div>
		</div>
		<div
			class="flex-1 flex items-center justify-center bg-white h-full w-full lg:w-auto lg:h-screen rounded-t-[20px] lg:rounded-none p-8"
		>
			<form class="w-full max-w-md space-y-6" on:submit|preventDefault={handleSubmit}>
				<div>
					<label for="name" class="block text-gray-600 text-sm font-medium mb-2"
						>Cardholder Name</label
					>
					<input
						style="color: black;"
						id="name"
						type="text"
						bind:value={cardholderName}
						placeholder="e.g. Habl Rans"
						class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-purple-500"
						required
					/>
				</div>
				<div>
					<label for="card" class="block text-gray-600 text-sm font-medium mb-2">Card Number</label>
					<input
						style="color: black;"
						id="card"
						type="number"
						bind:value={cardNumber}
						placeholder="e.g. 1234 5678 9123 0000"
						class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-purple-500"
						maxlength="19"
						required
					/>
				</div>
				<div class="flex space-x-4">
					<div>
						<label class="block text-gray-600 text-sm font-medium mb-2">EXP. Date (MM/YY)</label>
						<div class="flex space-x-2">
							<input
								style="color: black;"
								type="number"
								bind:value={expiryMonth}
								placeholder="MM"
								class="w-16 border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-purple-500"
								min="1"
								max="12"
								required
							/>
							<input
								style="color: black;"
								type="number"
								bind:value={expiryYear}
								placeholder="YY"
								class="w-16 border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-purple-500"
								min="0"
								max="99"
								required
							/>
						</div>
					</div>
					<div>
						<label for="cvc" class="block text-gray-600 text-sm font-medium mb-2">CVC</label>
						<input
							style="color: black;"
							id="cvc"
							type="number"
							bind:value={cvc}
							placeholder="e.g. 123"
							class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-purple-500"
							min="100"
							max="999"
							required
						/>
					</div>
				</div>
				<button
					class="w-full bg-purple-700 text-white py-3 rounded-lg shadow-md hover:bg-purple-800"
				>
					Confirm
				</button>
			</form>
		</div>
	{:else}
		<div
			class="flex flex-col items-center justify-center bg-white h-screen w-screen text-center p-8 space-y-4"
		>
			<div class="w-16 h-16 bg-purple-700 text-white rounded-full flex items-center justify-center">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-8 w-8"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M5 13l4 4L19 7"
					/>
				</svg>
			</div>
			<h2 class="text-2xl font-bold">Thank You!</h2>
			<p class="text-gray-500">We've added your card details</p>
			<button
				class="w-full max-w-sm bg-purple-700 text-white py-3 rounded-lg shadow-md hover:bg-purple-800"
				on:click={() => (isSubmitted = false)}
			>
				Continue
			</button>
		</div>
	{/if}
</div>
