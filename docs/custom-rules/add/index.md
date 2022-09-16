# Add a rule

## Format

A custom rule file `rules.txt` has the following format.

```
@[my rule name]
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [...]
```

A rule file can define multiple rules.

!!! example "For example, the default rule"

    ```
    @default
        @creative_menu_order

    @creative_menu_order
        ::custom_name
        ::creative_menu_group_index
        ::raw_id
        @default_nbt_rule

    @default_nbt_rule
        ::enchantments_score
        ::damage
        ::display_name
        ::potion_effect
        ::nbt_comparator
    ```

You can create multiple rule files: `rules.txt`, `rules.1.txt`, `rules.2.txt`, `rules.myname.txt`, `rules.*.txt` etc. They all should located in `.minecraft/config/inventoryprofiles` folder.

### Rule Format Explain

All rules prefixed with `@`/`::`. 
- `@` custom rule
- `::` native rule

```
@[my rule name]
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [...]
```

- First line defines rule name (always start with `@`)
- Second line and after define content (4 space indented)
    - Each line defines a sub rule
    - `(` `)` optional arguments

Native rule list: see [List of Native Rule & Parameter](natives)

!!! example "Example"

    A custom rule named `hello`
    - `apple` first
    - `diamond_sword` with durability low to high
    - rest by display name, then durability from high to low

    ```
    @hello
        apple
        diamond_sword(sub_rule_match = ::durability)
        ::display_name
        !::durability
    ```

    **Before**

    ![](https://i.imgur.com/Ll7J30E.png)

    **After**

    ![](https://i.imgur.com/LnXLpoZ.png)

### Wildcards

As of version 1.4.0 we support wildcards when it comes to item names so `stone*` will match every item that starts with `stone`

!!! example "Example"
    
    Suppose we want to have all shulker boxes first. The example below:
    - defines `all_boxes` rule that will match everything that ends on `shulker_box`
    - defines our new main rule `MyDefault` that instructs that all items matching `all_boxes` will be put first and the rest shell be sorted as the `default` for the mod. 

    ```
    @MyDefault
        @all_boxes
        @default

    @all_boxes
        *shulker_box
    ```

#### Wildcards considerations

* All wildcards are expanded before the rules file is parsed.

!!! example "The above example expanded"

    ```
    @all_boxes
        minecraft:black_shulker_box
        minecraft:blue_shulker_box
        minecraft:brown_shulker_box
        minecraft:cyan_shulker_box
        minecraft:gray_shulker_box
        minecraft:green_shulker_box
        minecraft:light_blue_shulker_box
        minecraft:light_gray_shulker_box
        minecraft:lime_shulker_box
        minecraft:magenta_shulker_box
        minecraft:orange_shulker_box
        minecraft:pink_shulker_box
        minecraft:purple_shulker_box
        minecraft:red_shulker_box
        minecraft:shulker_box
        minecraft:white_shulker_box
        minecraft:yellow_shulker_box
    ```

    Yes for IDs without namespace `minecraft` is assumed. If you need to specify modded items use the mod namespace. 

* The expansion is always done in alphabetical order.
* you can negate a wildcard with `!` for example `!*shulker_box` 

### Rule Override

You can override the default rule and any custom rule (multiple declaration for same rule name)
- Rules in the same file
    - later rule override earlier rule
- Rules in different files
    - sorted by file name (`rules.zzz.txt` override `rules.aaa.txt`)

!!! info "If the overridden custom rule failed to parse, it will find the earlier rule that is valid."

## Internal default rules

```
// Default rules file

@default
    @creative_menu_order

@creative_menu_order
    ::custom_name
    ::creative_menu_group_index
    ::raw_id
    @default_nbt_rule

@item_name
    ::display_name
    @default_nbt_rule

@item_id
    ::item_id
    @default_nbt_rule

@raw_id
    ::raw_id
    @default_nbt_rule

@default_nbt_rule
    ::enchantments_score
    ::damage
    ::display_name
    ::potion_effect
    ::nbt_comparator

@auto_refill_best
    @default_nbt_rule
```
