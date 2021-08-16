# Ajouter une règle

## Format

Un fichier de règle personnalisée `rules.txt` a le format suivant.

```
@[my rule name]
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [...]
```

Une règle peut en définir plusieurs autres. Par exemple (la règle par défaut):

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

Vous pouvez créer plusieurs fichiers de règle: `rules.txt`, `rules.1.txt`, `rules.2.txt`, `rules.myname.txt`, `rules.*.txt` etc. Ils doivent tous être dans le dossier `.minecraft/config/inventoryprofiles`.

### Explication du format des règles

Toutes les règles préfixées avec `@`/`::`.
- `@` règle personnalisée
- `::` règle native

```
@[my rule name]
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [@|::][rule name]([param] = [arg], [param] = [arg], [...])
    [...]
```

- La première ligne définit le nom de la règle (commence toujours par `@`)
- Les autres lignes définissent le contenu (indenté de 4 espaces)
    - Chaque ligne définit une sous-règle
    - `(` `)` arguments facultatifs

Liste des règles personnalisées natives: voir [Liste de règles & paramètres natifs](natives.md)

### Exemple

Une règle personnalisée `hello`
- `apple` en premier
- `diamond_sword` avec la durabilité dans l'ordre croissant
- par nom d'affichage, puis la durabilité dans l'ordre décroissant

```
@hello
    apple
    diamond_sword(sub_rule_match = ::durability)
    ::display_name
    !::durability
```

#### Avant

![](https://i.imgur.com/Ll7J30E.png)

#### Après

![](https://i.imgur.com/LnXLpoZ.png)

### Remplacement de règle

Vous pouvez remplacer la règle par défaut et n'importe quelle autre règle personnalisée (plusieurs déclaration pour le même nom)
- Règles dans le même fichier
    - les règles en dernier remplacent les premières
- Règles dans plusieurs fichiers
    - trié par nom de fichier (`rules.zzz.txt` remplace `rules.aaa.txt`)

Si la règle remplacée ne fonctionne pas, la première règle sera utilisée

## Règles internes par défaut

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
