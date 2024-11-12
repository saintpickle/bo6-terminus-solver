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
    class="h-screen w-screen flex flex-col items-center justify-between bg-slate-800 text-white text-center"
>
    <div class="flex flex-col items-center p-4 gap-y-8">
        <div class="flex flex-col gap-y-8">
            <h1
                class="text-xl p-6 rounded-lg bg-green-500 text-slate-800 font-bold md:text-6xl"
            >
                Black Ops 6 Terminus Calculator
            </h1>
            <p class="text-sm md:text-lg">
                Let's save you that 5K, just get a friend to hold the zombies or
                pause your game.
            </p>
        </div>

        <div class="flex flex-col gap-y-6 md:gap-x-6">
            <div class="flex flex-col gap-y-12 md:flex-row md:gap-x-12">
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

            <p class="text-4xl">
                <span class="text-green-500">Code:</span>
                {code}
            </p>
        </div>
    </div>

    <footer
        class="w-full text-center py-4 bg-green-500 text-slate-800 font-bold"
    >
        <p class="text-lg">BO6 Terminus Calculator</p>
    </footer>
</div>
