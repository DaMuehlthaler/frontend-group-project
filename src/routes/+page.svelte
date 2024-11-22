<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
	href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300..700&display=swap"
	rel="stylesheet"
/>
<img src="/images/bg-card-front.png" alt="ihhh" class="absolute z-10 top-[22%] left-[10%] w-96" />
<img src="/images/bg-card-back.png" alt="ihhh" class="absolute z-20 bottom-[20%] left-[16%] w-96" />
<div class="flex">
	<img src="/images/bg-main-desktop.png" alt="ihhh" class="h-screen -z-10" />
	<div class="h-screen w-screen bg-white flex flex-col justify-center items-center">
		<div class="w-[440px] h-fit">
			<form action="/">
				<label for="name" class="text-grey uppercase tracking-wide font-condensed"
					>Cardholder Name</label
				>
				<input
					id="name"
					type="text"
					placeholder="e.g. Habl Rans"
					class="input input-bordered w-full bg-white mb-8"
					required
				/>
				<br />
				<label for="card" class="text-grey uppercase tracking-wide font-space-grotesk"
					>Card Number</label
				>
				<input
					type="number"
					maxlength="10"
					id="card"
					required
					placeholder="1234 5678"
					class="input input-bordered w-full mb-8 bg-white"
				/>
				<div class="w-full flex gap-[85px]">
					<label for="expiry" class="text-grey uppercase tracking-wide">EXP. Date (MM/YY)</label>
					<label for="cvc" class="text-grey uppercase tracking-wide text-right mr">CVC</label>
				</div>

				<input
					type="number"
					maxlength="2"
					required
					placeholder="MM"
					class="input input-bordered w-1/4 bg-white mb-8"
				/>

				<input
					type="number"
					maxlength="2"
					required
					placeholder="YY"
					class="input input-bordered bg-white w-1/4"
				/>

				<input
					type="number"
					maxlength="3"
					required
					placeholder="e.g.123"
					class="input input-bordered w-[48%] bg-white mb-8"
				/>
				<br />
				<button class="btn btn-primary border-none bg-black w-full text-white">Confirm</button>
			</form>
		</div>
	</div>
</div>

