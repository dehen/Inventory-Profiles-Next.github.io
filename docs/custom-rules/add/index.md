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

Native rule list: see [List of Native Rule & Parameter](List-of-Native-Rule-&-Parameter)

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
