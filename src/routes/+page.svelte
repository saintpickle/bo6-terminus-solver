<script>
    let x = $state(null);
    let y = $state(null);
    let z = $state(null);

    let state = $derived([x, y, z]);

    let code = $derived.by(() => {
        let a = "00";
        let b = "00";
        let c = "00";

        if (!state.includes(null)) {
            a = x * 2 + 11;
            b = 2 * z + y - 5;
            c = y + z - x;
        }

        return `${a} ${b} ${c}`;
    });

    function reset() {
        x = null;
        y = null;
        z = null;
    }
</script>

<div
    class="h-screen w-screen gap-y-8 flex flex-col items-center justify-between bg-slate-800 text-white text-center md:justify-center"
>
    <div class="flex flex-col p-4 gap-y-8">
        <h1
            class="text-xl p-6 rounded-lg bg-green-500 text-slate-800 font-bold md:text-6xl"
        >
            Black Ops 6 Terminus Calculator
        </h1>
        <p class="text-md md:text-lg">
            Let's save you that 5K, just get a friend to hold the zombies or
            pause your game.
        </p>

        <p class="text-4xl">
            <span class="text-green-500">Code:</span>
            {code}
        </p>
    </div>

    <div class="flex flex-col gap-y-6 md:gap-x-6">
        <div class="flex flex-col gap-y-12 md:flex-row md:gap-x-12">
            <input
                type="number"
                class="w-full p-2 text-black text-xl border-4 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="X Value"
                pattern="[0-9]*"
                inputmode="numeric"
                bind:value={x}
            />

            <input
                type="number"
                class="w-full p-2 text-black text-xl border-4 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="Y Value"
                pattern="[0-9]*"
                inputmode="numeric"
                bind:value={y}
            />

            <input
                type="number"
                class="w-full p-2 text-black text-xl border-4 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="Z Value"
                pattern="[0-9]*"
                inputmode="numeric"
                bind:value={z}
            />
        </div>

        <button
            onclick={reset}
            class="px-4 py-2 font-medium shadow transition-colors duration-300 rounded-md text-slate-800 bg-green-500 hover:bg-green-500/90"
            >Reset Code
        </button>
    </div>
    <div class="md:hidden"></div>
</div>
