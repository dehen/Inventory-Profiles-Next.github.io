# Règles & paramètres natifs

## Paramètre
```
reverse
    true/false
sub_rule
    [any rule]
```
```
blank_string
    first/last
string_compare
    unicode/ignore_case/locale
locale
    mc
    sys
    [any lang tag]
strength
    primary/secondary/tertiary/identical
logical
    true/false
```
```
number_order
    ascending/descending
```
```
match
    first/last
sub_rule_match
    [any rule]
sub_rule_not_match
    [any rule]
nbt
    [any nbt tag]
allow_extra
    true/false
require_nbt
    required/no_nbt/not_required
tag_name
    [any tag name]
item_name
    [any item name]
```
```
nbt_path
    [any nbt path]
not_found
    first/last
```
## Règle native
#### `[all rule]`
- `(reverse = false, sub_rule = ::none)`

#### `::none`

#### `[string type rule]`
- `(blank_string = last, string_compare = locale, locale = mc, strength = primary, logical = true)`
```
::display_name
::custom_name
::translated_name
::translation_key (string_compare = unicode)
::item_id         (string_compare = unicode)
::potion_name     (string_compare = unicode)
```

#### `[number type rule]`
- `(number_order = ascending)`
```
::raw_id
::creative_menu_group_index
::damage
::max_damage
::durability
::enchantments_score(number_order = descending)
```

#### `[boolean type rule]`
- `(match = first, sub_rule_match = ::none, sub_rule_not_match = ::none)`
```
::has_custom_name
::is_damageable
::match_nbt(nbt = {}, allow_extra = true)
::is_tag(tag_name/*required*/, require_nbt = not_required, nbt = {}, allow_extra = true)
::is_item(item_name/*required*/, require_nbt = not_required, nbt = {}, allow_extra = true)
```

#### `::by_nbt`
- `(nbt_path/*required*/, not_found = last)`
- parameters of `[string type rule]`, `[number type rule]`

#### `::nbt_comparator`
#### `::potion_effect`

## Raccourcis de syntax (sucre syntaxique)
### sub_rule
```
[::a](sub_rule = [::b])
<=>
[::a]
[::b]
```
### reverse
```
[::a](reverse = true)
<=>
![::a]
```
### is_tag
```
::is_tag(tag_name = [tag])
<=>
#[tag]
```
### is_item
```
::is_item(item_name = [item])
<=>
[item]
```
### nbt for is_tag/is_item
```
#[tag]{}
<=>
::is_tag(tag_name = [tag], require_nbt = required)
```
```
#[tag]{ [nbt] }( [other arguments...] )
<=>
::is_tag(tag_name = [tag], require_nbt = required, nbt = { [nbt] }, [other arguments...])
```
