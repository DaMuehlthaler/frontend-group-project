<div class="flex">
<img src="/images/bg-main-desktop.png" alt="ihhh" class="h-screen -z-10" />
<div class="h-screen w-screen bg-white flex flex-col justify-center items-center">
    <div class="w-[440px] h-fit">
	<form action="/">
        <label for="name" class="text-black uppercase tracking-wide font-condensed">Cardholder Name</label>
		<input
            id="name"
			type="text"
			placeholder="e.g. Hansi Hinterseer"
			class="input input-bordered w-full   bg-white mb-8"
            required
		/>
		<br />
        <label for="card" class="text-black uppercase tracking-wide">Card Number</label>
		<input type="number" id="card" required placeholder="1234 5678" class="input input-bordered w-full mb-8  bg-white" />
		<br />
		<input type="number" required placeholder="MM" class="input input-bordered w-1/4 bg-white mb-8" />

		<input type="Number" required placeholder="YY" class="input input-bordered  bg-white w-1/4" />

		<input type="number" required placeholder="e.g.123" class="input input-bordered w-[48%]  bg-white mb-8" />
        <br>
        <button class="btn btn-primary bg-black w-full text-white">Confirm</button>
	</form>
    </div>
</div>
</div>
