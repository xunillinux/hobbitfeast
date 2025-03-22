<script>
    import { fade } from 'svelte/transition';
    import { scale } from 'svelte/transition';

    const menu = [
        { title: "Breakfast", items: [
            "Pancakes with Sour Cream, Bacon & Maple Syrup",
            "Fresh fruit juice or herbal tea"
        ]},
        { title: "Second Breakfast", items: [
            "Smoked Carrot Salmon with Bagles & Cream Cheese",
            "Chai Latte or fresh apple juice"
        ]},
        { title: "Elevenses", items: [
            "Lembas Bread with Date and Spring Onion Dip",
            "Spiced apple cider"
        ]},
        { title: "Luncheon", items: [
            "Crispy grated TATERS with Garlic & Herbs",
            "Lemon Cider"
        ]},
        { title: "Afternoon Tea", items: [
            "Cake",
            "Warm oat milk with cinnamon"
        ]},
        { title: "Dinner", items: [
            "Snack Sandwiches (Cucumber / Cracker & Cream Cheese)",
            "Chai tea or English breakfast tea"
        ]},
        { title: "Supper", items: [
            "Alsatian Flatbread",
            "Garlic, Onions, Mushrooms, Bacon",
            "Ginger and Mint infused water"
        ]},
    ];
</script>

<style>
    @keyframes hobbitSkip {
        0%   { transform: translateX(-100px) translateY(0px) scaleX(-1); } /* Start Left */
        10%  { transform: translateX(-80px) translateY(-10px) scaleX(-1); } /* Hop */
        20%  { transform: translateX(-60px) translateY(0px) scaleX(-1); } /* Land */
        30%  { transform: translateX(-40px) translateY(-12px) scaleX(-1); } /* Hop */
        40%  { transform: translateX(-20px) translateY(0px) scaleX(-1); } /* Land */
        50%  { transform: translateX(0px) translateY(-15px) scaleX(-1); } /* Hop */
        60%  { transform: translateX(20px) translateY(0px) scaleX(-1); } /* Land */
        70%  { transform: translateX(40px) translateY(-12px) scaleX(-1); } /* Hop */
        80%  { transform: translateX(60px) translateY(0px) scaleX(-1); } /* Land */
        90%  { transform: translateX(80px) translateY(-10px) scaleX(-1); } /* Hop */
        100% { transform: translateX(100px) translateY(0px) scaleX(-1); } /* Land (Still Left-Facing) */
    }

    @keyframes hobbitSkipBack {
        0%   { transform: translateX(100px) translateY(0px) scaleX(1); } /* Start Right */
        10%  { transform: translateX(80px) translateY(-10px) scaleX(1); } /* Hop */
        20%  { transform: translateX(60px) translateY(0px) scaleX(1); } /* Land */
        30%  { transform: translateX(40px) translateY(-12px) scaleX(1); } /* Hop */
        40%  { transform: translateX(20px) translateY(0px) scaleX(1); } /* Land */
        50%  { transform: translateX(0px) translateY(-15px) scaleX(1); } /* Hop */
        60%  { transform: translateX(-20px) translateY(0px) scaleX(1); } /* Land */
        70%  { transform: translateX(-40px) translateY(-12px) scaleX(1); } /* Hop */
        80%  { transform: translateX(-60px) translateY(0px) scaleX(1); } /* Land */
        90%  { transform: translateX(-80px) translateY(-10px) scaleX(1); } /* Hop */
        100% { transform: translateX(-100px) translateY(0px) scaleX(1); } /* Land (Still Right-Facing) */
    }

    #dancingSvg {
        animation: hobbitSkip 3s ease-in-out infinite alternate,
                hobbitSkipBack 3s ease-in-out infinite alternate 3s,
                flipHobbit 6s ease-in-out infinite;
    }
</style>

<div class="min-h-screen flex flex-col items-center py-8 bg-cover bg-center text-center" style="background-image: url('/images/background.webp');">
    <div 
        class="relative w-11/12 max-w-xl flex flex-col items-center p-6 shadow-lg border-4 border-yellow-900 rounded-lg text-center" 
        style="background: linear-gradient(180deg, #f5e1b8 0%, #e3c99f 100%); padding: 2rem; box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.2); border-radius: 12px; border: 3px solid #8B5E3B;"
        in:fade
    >
        <h1 class="flex items-center justify-center text-3xl font-bold text-brown-900 mb-6" in:scale={{ duration: 500 }}>
            <img src="/images/favicon.webp" alt="Hobbit Logo" class="w-12 h-12 rounded-full mr-4" />
            Hobbit Feast
        </h1>
        {#each menu as meal, i}
            <div 
                class="border-b border-gray-600 pb-4 mb-4 w-full last:border-none text-center" 
                in:fade={{ delay: i * 100, duration: 400 }}
            >
                <h2 class="text-2xl font-semibold text-brown-800 mb-2">{meal.title}</h2>
                <ul class="list-none p-0 text-brown-700">
                    {#each meal.items as item}
                        <li 
                            class="text-md py-1 transition-transform transform hover:scale-105 hover:text-yellow-700 cursor-pointer"
                            in:fade
                        >
                            {item}
                        </li>
                    {/each}
                </ul>
            </div>
        {/each}

        <svg id="dancingSvg" width="100px" height="100px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <image x="0px" y="0px" width="100px" height="100px" xlink:href="/images/dancinghobbits.svg" />
        </svg>
        

    </div>
</div>