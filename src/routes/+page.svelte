<script>
    export let menu = [
        { title: "Breakfast (8:00 AM)", items: [
            "Pancakes with Sour Cream, Bacon & Maple Syrup",
            "Fresh fruit juice or herbal tea"
        ]},
        { title: "Second Breakfast (10:00 AM)", items: [
            "Smoked Carrot Salmon with Rustic Bread & Cream Cheese",
            "Black tea with oat milk or fresh apple juice"
        ]},
        { title: "Elevenses (11:30 AM)", items: [
            "Lembas Bread with Date and Spring Onion Dip",
            "Peppermint tea or spiced cider"
        ]},
        { title: "Luncheon (1:00 PM)", items: [
            "Hearty Stew with 'Taters' (Potato, Root Veggies & Lentils in a Rich Broth)",
            "Served with fresh bread or dumplings",
            "Homemade elderflower cordial"
        ]},
        { title: "Afternoon Tea (4:00 PM)", items: [
            "Tea Sandwiches (Cucumber & Cream Cheese / Mushroom Pâté)",
            "Chai tea or English breakfast tea"
        ]},
        { title: "Dinner (7:00 PM)", items: [
            "Stuffed Butternut Squash with Cranberries & Walnuts",
            "Roasted 'Taters' with Garlic & Herbs",
            "Mulled wine or spiced cider"
        ]},
        { title: "Supper (9:00 PM)", items: [
            "Rustic Bread with Almond Butter & Jam",
            "Mixed Nuts & Dried Fruits",
            "Warm oat milk with cinnamon"
        ]}
    ];
</script>

<div class="min-h-screen flex flex-col items-center py-8 bg-cover bg-center text-center" style="background-image: url('/images/background.webp');">
    <div class="relative w-11/12 max-w-xl flex flex-col items-center p-6 shadow-lg border-4 border-yellow-900 rounded-lg text-center" style="background: linear-gradient(180deg, #f5e1b8 0%, #e3c99f 100%); padding: 2rem; box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.2); border-radius: 12px; border: 3px solid #8B5E3B;">
        <h1 class="flex items-center justify-center text-3xl font-bold text-brown-900 mb-6">
            <img src="/images/favicon.webp" alt="Hobbit Logo" class="w-12 h-12 rounded-full mr-4" />
            Hobbit Feast
        </h1>
        {#each menu as meal}
            <div class="border-b-1 border-gray-600 pb-4 mb-4 w-full last:border-none text-center">
                <h2 class="text-2xl font-semibold text-brown-800 mb-2">{meal.title}</h2>
                <ul class="list-none p-0 text-brown-700">
                    {#each meal.items as item}
                        <li class="text-md py-1">{item}</li>
                    {/each}
                </ul>
            </div>
        {/each}
    </div>
</div>
