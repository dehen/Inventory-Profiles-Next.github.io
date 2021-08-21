# <span class="twemoji"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="m433.941 129.941-83.882-83.882A48 48 0 0 0 316.118 32H48C21.49 32 0 53.49 0 80v352c0 26.51 21.49 48 48 48h352c26.51 0 48-21.49 48-48V163.882a48 48 0 0 0-14.059-33.941zM224 416c-35.346 0-64-28.654-64-64 0-35.346 28.654-64 64-64s64 28.654 64 64c0 35.346-28.654 64-64 64zm96-304.52V212c0 6.627-5.373 12-12 12H76c-6.627 0-12-5.373-12-12V108c0-6.627 5.373-12 12-12h228.52c3.183 0 6.235 1.264 8.485 3.515l3.48 3.48A11.996 11.996 0 0 1 320 111.48z"></path></svg></span> Profiles

## Before You Start

You will need to set at least "Save the current state as "Saved" Profile" of the hotkeys in the Profiles section of "Hotkeys".
Tinted green in this screenshot.

<img src="/assets/profiles-save-profile-hotkeys-config.png">

Of course you can set the set of the hotkeys while you're at it.

## Your First Profile(s)

1. Fill your hot bar and equipment slots with your favourite gear.
2. Press the hotkey you configured above. **Note** that the hotkey **only works** when you have your inventory opened.
3. Repeat for any combination of items you want.

You are still not done. You have created a configuration, but you will need to edit it to make it work.

## Some assembly required

The in-game profiles management is not ready yet. You will need to manually edit the configuration. Go to "Edit Profiles" and click the "Profiles Config" button.

<img src="/assets/edit-profiles-open-config.png">

## The Basics

Let's say we have saved 3 profiles:

```profiles
profile Saved activate HOT1
	HOT1
		"minecraft:netherite_pickaxe" -> "Enchantments" : [{id:"minecraft:efficiency",lvl:5},{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:silk_touch",lvl:1},{id:"minecraft:mending",lvl:1}]
	CHEST
		"minecraft:elytra" -> "Enchantments" : [{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:mending",lvl:1}]

profile Saved activate HOT1
	HOT1
		"minecraft:netherite_pickaxe" -> "Enchantments" : [{id:"minecraft:mending",lvl:1},{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:efficiency",lvl:5},{id:"minecraft:fortune",lvl:3}]
	CHEST
		"minecraft:elytra" -> "Enchantments" : [{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:mending",lvl:1}]

profile Saved activate HOT1
	CHEST
		"minecraft:netherite_chestplate" -> "Enchantments" : [{id:"minecraft:fire_protection",lvl:4},{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:mending",lvl:1}]
```

To make them usable you need to set their names, change `Saved` in `#!profiles profile Saved` to something unique for all 3 of them.

!!! warning "No spaces allowed in the name."

Go back to the screenshot above. Now is a good time to fill those "Quick Profile" names, and if you didn't yet, assign them hotkeys.

Once you are ready with the names, you need to reload the configuration. The default hotkey is ++r+y++ .

That's it you are ready to go... 

BUT if you want to use the full potential of the Profiles continue reading.

## The long explanation

### Let's start from the beginning

The line `#!profiles profile Saved activate HOT1` says that we are starting a `#!profiles profile` with the name `Saved`
and every time we switch to this profile it will `#!profiles activate` the first hotbar slot `#!profiles HOT1`. If you remove `#!profiles activate HOT1` when you 
activate the Profile the selected hotbat slot won't change.  

### Slot definitions

On the next line we have `#!profiles HOT1`. This means that the lines below will contain the desired equipment in this slot. 

`#!profiles "minecraft:netherite_pickaxe"` we want to have a Netherite Pickaxe in this slot with the following `#!profiles -> "Enchantments" : `.
The next part is a list of the enchantments we want the item in this slot to have. This is the minimum set of the enchantments we desire.
For example, suppose we want a profile that always puts a Silk Touch pickaxe in hotbar 1 we can specify:

```profiles
"minecraft:netherite_pickaxe" -> "Enchantments" : [{id:"minecraft:silk_touch",lvl:1}]
```

This means that when activating the Profile the best available Netherite Pickaxe with Silk Touch will be put in that slot.
But this also means that if we have a bunch of Netherite Pickaxes without Silk Touch none of them will be put in the slot.

#### "What if I just care about the Silk Touch?"

Now we are talking! Profiles can be very powerful if you want them to be. Below we define that hotbar 1 should contain the best Silk Touch pickaxe we have.

```profiles
profile Silky activate HOT1
	HOT1
		"minecraft:netherite_pickaxe" -> "Enchantments" : [{id:"minecraft:silk_touch",lvl:1}]
		"minecraft:diamond_pickaxe" -> "Enchantments" : [{id:"minecraft:silk_touch",lvl:1}]
		"minecraft:iron_pickaxe" -> "Enchantments" : [{id:"minecraft:silk_touch",lvl:1}]

	CHEST
		"minecraft:elytra" -> "Enchantments" : [{id:"minecraft:unbreaking",lvl:3},{id:"minecraft:mending",lvl:1}]
```

So a hotbar slot definition can contain multiple items and the priority is defined by the order in the configuration.
With the above we define that want a Silk Touch pickaxe and first choice would be Netherite, then Diamond and last Iron. 

#### "And if I don't really care about enchantments?"

Every thing after the type `#!profiles "minecraft:netherite_pickaxe"` of the item can be omitted. The above becomes:

```profiles
profile Digger activate HOT1
	HOT1
		"minecraft:netherite_pickaxe"
		"minecraft:diamod_pickaxe"
		"minecraft:iron_pickaxe"
```

This will just select the "best" pickaxe we have at the moment. And by "best" we mean the one with most enchantments and durability.

#### Potions are different?!

Although potions look like enchanted items, they are not.

Here is how potion definitions look like. Except the syntax, there are not many differences from how enchantments are handled.

```profiles
	HOT5
		"minecraft:potion" -> "Potion" : {id:"minecraft:long_invisibility"}
		"minecraft:lingering_potion" -> "Potion" : {id:"minecraft:long_invisibility"}
	HOT8
		"minecraft:splash_potion" -> "Potion" : {id:"minecraft:regeneration"}
```

You can imagine that only having `#!profiles "minecraft:splash_potion"` doesn't make much sense, but you can.
You will end with a Splash Potion in that slot... But which one?! Nobody knows...

### Some advanced uses

You can define some single item profiles to make you live easier. For example 1 Profile for Elytra and 1 for Chest Plate, 
so we will be able to switch between them faster. How about having dedicated profile with Water Bucket or Fire resistance
potion in case you fall in lava? The only limit is your imagination.
