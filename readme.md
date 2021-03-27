# genshin-db

### Genshin Impact JSON database with a robust searching API! Updated to version 1.4. Sources from the fandom wiki and GenshinData repo.

------------------------------------

Flexibly search and get the information of characters, talents, constellations, weapons, weapon material, talent material, artifacts, food recipes.

All in-game languages are supported for query and result. (translations available only for characters, talents, constellations, weapons, artifacts currently).

Start with:

```js
const genshindb = require('genshin-db');
```

REFER TO [EXAMPLES.md](https://github.com/theBowja/genshin-db/blob/main/examples.md) since the readme below isn't detailed.

Every input string to the query parameter will be **autocompleted** to match possible values. This means doing something like genshin.characters('amb') will give the same results as genshin.characters('amber'). If there are no results, then **undefined** will be returned.

Every update will probably change the format for some data. If you need to know the data format for some specific version of this library, you can go to the github and switch to the tag version you're on. Then go into the data folder and look at the data to find the format. Don't look into the template folder since it isn't up-to-date.

If you need help or have questions, you can talk to me in [my discord](https://discord.gg/MHhYnRSC).

## Table of Contents

- [genshindb.setOptions(opts)](#genshindbsetoptionsopts)
- [genshindb.getOptions()](#genshindbgetoptions)
- [genshindb.characters(query[, opts])](#genshindbcharactersquery-opts)
- [genshindb.talents(query[, opts])](#genshindbtalentsquery-opts)
- [genshindb.constellations(query[, opts])](#genshindbconstellationsquery-opts)
- [genshindb.weapons(query[, opts])](#genshindbweaponsquery-opts)
- [genshindb.weaponmaterialtypes(query[, opts])](#genshindbweaponmaterialtypesquery-opts)
- [genshindb.talentmaterialtypes(query[, opts])](#genshindbtalentmaterialtypesquery-opts)
- [genshindb.artifacts(query[, opts])](#genshindbartifactsquery-opts)
- [genshindb.recipes(query[, opts])](#genshindbrecipesquery-opts)
- [genshindb.elements(query[, opts])](#genshindbelementsquery-opts)
- [genshindb.rarity(query[, opts])](#genshindbrarityquery-opts)

## genshindb.setOptions(opts)

The following are the **default options** that the library starts off with. If you want to change it, then call setOptions.

```js
{
    matchAliases: true, // Allows the matching of aliases.
    matchCategories: false, // Allows the matching of categories. If true, then returns an array if it matches.
    verboseCategories: false, // Used if a category is matched. If true, then replaces each string name in the array with the data object instead.
    queryLanguages: ["English"], // Array of languages that your query will be searched in.
    resultLanguage: "English" // Output language that you want your results to be in.
}
````

If **matchCategories** is set to true, then the query may match a category like genshindb.characters('Geo'). An array of string names will be returned. If **verboseCategories** is set to true, then an array of objects will be returned instead.

Supported languages options are: ChineseSimplified, ChineseTraditional, English, French, German, Indonesian, Japanese, Korean, Portuguese, Russian, Spanish, Thai, Vietnamese.

## genshindb.getOptions()

## genshindb.characters(query[, opts])

Returns the profile info for characters.

Possible query inputs include: character names, character titles, constellation names, birthday months, elements, substats, weapon types, talent level-up material types, genders, regions, rarities, and 'name' for the list of all characters.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbcharactersquery-opts) to see example inputs and outputs for this function.

## genshindb.talents(query[, opts])

Returns the combat skills and passive skills for characters.

Possible query inputs include: character names.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbtalentsquery-opts) to see example inputs and outputs for this function.

## genshindb.constellations(query[, opts])

Returns the constellation information for characters.

Possible query inputs include: character names.

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbconstellationsquery-opts) to see example inputs and outputs for this function.

## genshindb.weapons(query[, opts])

Possible inputs for query parameter are:

- all weapon names
- all weapon types
- all rarities
- all weapon ascension material types
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbweaponsquery-opts) to see example inputs and outputs for this function.

## genshindb.weaponmaterialtypes(query[, opts])

Possible inputs for query parameter are:

- all weapon ascension material names
- all days of the week
- all regions
- all domains of forgery
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbweaponmaterialtypesquery-opts) to see example inputs and outputs for this function.

## genshindb.talentmaterialtypes(query[, opts])

Possible inputs for query parameter are:

- all talent book names
- all days of the week
- all regions
- all domains of mastery
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbtalentmaterialtypesquery-opts) to see example inputs and outputs for this function.


## genshindb.artifacts(query[, opts])

Possible inputs for query parameter are:

- all artifact set names
- all rarities
- "names"

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbartifactsquery-opts) to see example inputs and outputs for this function.

## genshindb.recipes(query[, opts])

Possible inputs for query parameter are:

- all recipe names
- all rarities
- all recipe types
- all ingredients
- all buffs
- all characters with specialty dishes

Check out [categories.json](https://github.com/theBowja/genshin-db/blob/main/src/english/categories.json) file to see choices for each category.\
Check out [examples.md](https://github.com/theBowja/genshin-db/blob/main/examples.md#genshindbrecipesquery-opts) to see example inputs and outputs for this function.

## genshindb.elements(query[, opts])

Input the name of an element

## genshindb.rarity(query[, opts])

dunno about this

---------------------------

"Robust" makes the description sound cooler doesn't it?

My ambition for this library is to include most of the relevant genshin data so it can be downloaded and used easily with any project. Currently the data is manually entered. I would appreciate it a lot if someone could provide me datamined files of the live version.

## Webpack

If you want to build a webpack just do `npm run build` and it'll appear in the **dist/genshindb.js**. Then you can call all the query functions from above using genshindb as the variable. Or you can change the options in **webpack.config.js** to better fit how you want to use it.