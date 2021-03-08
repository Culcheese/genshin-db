# genshin-db

### Genshin Impact JSON database with a robust searching API! Updated to version 1.3. Sources from the fandom wiki and GenshinData repo.

------------------------------------

Flexibly search and get the information of characters, talents, constellations, weapons, weapon material, talent material, artifacts, food recipes.

All in-game languages are supported for query and result. (only for characters, talents, constellations)

Start with:

```js
const genshin = require('genshin-db');
```

Refer to [EXAMPLES.md](https://github.com/theBowja/genshin-db/blob/main/examples.md) since this readme isn't really good.

Every input string to the query parameter will be **autocompleted** to match possible values. This means doing something like genshin.characters('amb') will give the same results as genshin.characters('amber'). If there are no results, then **undefined** will be returned.

Please join [my discord](https://discord.gg/MHhYnRSC) and talk to me.

## Table of Contents

- [genshin.setOptions(opts)](#genshinsetoptionsopts)
- [genshin.getOptions()](#genshingetoptions)
- [genshin.characters(query[, opts])](#genshincharactersquery-opts)
- [genshin.talents(query[, opts])](#genshintalentsquery-opts)
- [genshin.constellations(query[, opts])](#genshinconstellationsquery-opts)
- [genshin.weapons(query[, opts])](#genshinweaponsquery-opts)
- [genshin.weaponmaterialtypes(query[, opts])](#genshinweaponmaterialtypesquery-opts)
- [genshin.talentmaterialtypes(query[, opts])](#genshintalentmaterialtypesquery-opts)
- [genshin.artifacts(query[, opts])](#genshinartifactsquery-opts)
- [genshin.recipes(query[, opts])](#genshinrecipesquery-opts)
- [genshin.elements(query[, opts])](#genshinelementsquery-opts)
- [genshin.rarity(query[, opts])](#genshinrarityquery-opts)

## genshin.setOptions(opts)

Default options

```js
{
    verbose: false, // used for replacing string names from categories with data object
    nameonly: false, // set this to true if you don't want your query to match any categories or aliases
    querylanguages: ["English"], // array of languages that your query will be searched in
    resultlanguage: "English"
}
````

If the query matches a category where there may be multiple results like genshin.characters('Geo'), then an array of names will be returned. If **verbose** is set to true, then an array of objects will be returned instead. If **nameonly** is set to true, then the query search will be limited to only matching names instead.

Supported languages options are: ChineseSimplified, ChineseTraditional, English, French, German, Indonesian, Japanese, Korean, Portuguese, Russian, Spanish, Thai, Vietnamese.

## genshin.getOptions()

## genshin.characters(query[, opts])

Returns the profile info for characters.

Possible query inputs include: character names, constellation names, birthday months, elements, substats, weapon types, talent level-up material types, genders, regions, rarities, and 'name' for the list of all characters.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshincharactersquery-opts) to see example inputs and outputs for this function.

## genshin.talents(query[, opts])

Returns the combat skills and passive skills for characters.

Possible query inputs include: character names.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshintalentsquery-opts) to see example inputs and outputs for this function.

## genshin.constellations(query[, opts])

Returns the constellation information for characters.

Possible query inputs include: character names.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshinconstellationsquery-opts) to see example inputs and outputs for this function.

## genshin.weapons(query[, opts])

Possible inputs for query parameter are:

- all weapon names
- all weapon types
- all rarities
- all weapon ascension material types
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshinweaponsquery-opts) to see example inputs and outputs for this function.

## genshin.weaponmaterialtypes(query[, opts])

Possible inputs for query parameter are:

- all weapon ascension material names
- all days of the week
- all regions
- all domains of forgery
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshinweaponmaterialtypesquery-opts) to see example inputs and outputs for this function.

## genshin.talentmaterialtypes(query[, opts])

Possible inputs for query parameter are:

- all talent book names
- all days of the week
- all regions
- all domains of mastery
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshintalentmaterialtypesquery-opts) to see example inputs and outputs for this function.


## genshin.artifacts(query[, opts])

Possible inputs for query parameter are:

- all artifact set names
- all rarities
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshinartifactsquery-opts) to see example inputs and outputs for this function.

## genshin.recipes(query[, opts])

Possible inputs for query parameter are:

- all recipe names
- all rarities
- all recipe types
- all ingredients
- all buffs
- all characters with specialty dishes

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshinrecipesquery-opts) to see example inputs and outputs for this function.

## genshin.elements(query[, opts])

Input the name of an element

## genshin.rarity(query[, opts])

dunno about this

---------------------------

"Robust" makes the description sound cooler doesn't it?

My ambition for this library is to include most of the relevant genshin data so it can be downloaded and used easily with any project. Currently the data is manually entered. I would appreciate it a lot if someone could provide me datamined files of the live version.

## Webpack

If you want to build a webpack just do `npm run build` and it'll appear in the **dist/genshindb.js**. Then you can call all the query functions from above using GenshinDB as the variable. Or you can change the options in **webpack.config.js** to better fit how you want to use it.