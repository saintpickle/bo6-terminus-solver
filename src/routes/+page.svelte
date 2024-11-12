<script>
    let x = $state();
    let y = $state();
    let z = $state();

    let code = $derived.by(() => {
        let a = "00";
        let b = "00";
        let c = "00";

        if (x) {
            a = x * 2 + 11;
        }

        if (x && y && z) {
            b = 2 * z + y - 5;
            c = y + z - x;
        }

        return `${a} ${b} ${c}`;
    });
</script>

<div
    class="h-screen p-4 flex flex-col items-center justify-center bg-slate-800 text-white text-center md:justify-normal md:p-32"
>
    <div class="flex flex-col items-center gap-y-8">
        <h1 class="text-3xl md:text-6xl">
            Black Ops 6 Terminus Equation Solver
        </h1>
        <p class="text-sm md:text-lg">
            Let's save you that 5K, just get a friend to hold the zombies or
            pause your game.
        </p>
        <div class="flex flex-col gap-x-4 gap-y-4 md:flex-row">
            <input
                type="number"
                class="w-full p-2 text-black text-xl border-2 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="X Value"
                bind:value={x}
            />

            <input
                type="number"
                class="w-full p-2 text-black text-xl border-2 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="Y Value"
                bind:value={y}
            />

            <input
                type="number"
                class="w-full p-2 text-black text-xl border-2 rounded-lg shadow outline-none focus:border-green-500"
                placeholder="Z Value"
                bind:value={z}
            />
        </div>
        <p class="text-4xl"><span class="text-green-500">Code:</span> {code}</p>
    </div>
</div>
