---
date: 2025-08-23
comments: true
tags:
    - minecraft
    - modding
---
# explaining some kubejs
<!-- more -->
!!! Note "Mods required"
    [https://www.curseforge.com/minecraft/mc-mods/kubejs](https://www.curseforge.com/minecraft/mc-mods/kubejs)

## How do you use kubeJS?
I would highly recommend reading this: [https://kubejs.com/wiki/tutorials/getting-started](https://kubejs.com/wiki/tutorials/getting-started)
### Recipes
`kubejs/server_scripts/<WHATEVER>.js`
```{ .js .copy title="recipes.js" }
ServerEvents.recipes(event => {
    //Put recipes in here (1)
})
```

??? example
    ```{ .js .copy title="recipes.js" }
    ServerEvents.recipes(event => {
        event.shaped(
            Item.of('minecraft:stone', 3), // arg 1: output
            [
                'A B',
                ' C ', // arg 2: the shape (array of strings)
                'B A'
            ],
            {
                A: 'minecraft:andesite',
                B: 'minecraft:diorite',  //arg 3: the mapping object
                C: 'minecraft:granite'
            }
        );
        
        event.recipes.tfc.barrel_sealed(5000)
            .outputItem('8x minecraft:mud')
            .inputs('#tfc:high_quality_cloth', TFC.fluidStackIngredient('#tfc:dyes', 1000))
    })
    ```

## TFC Barrel Sealed
!!! Note "Mods required"
    [https://www.curseforge.com/minecraft/mc-mods/kubejs-tfc](https://www.curseforge.com/minecraft/mc-mods/kubejs-tfc)

[https://notenoughmail.github.io/kubejs_tfc/1.20.1/recipes/#barrel-sealed](https://notenoughmail.github.io/kubejs_tfc/1.20.1/recipes/#barrel-sealed)
```js
event.recipes.tfc.barrel_sealed(5000)
    .outputItem('8x minecraft:mud')
    .inputs('#tfc:high_quality_cloth', TFC.fluidStackIngredient('#tfc:dyes', 1000))
```