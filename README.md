# bella_spina
magireco scenario patches

patching from translated ones to latest jp versions

- patches are in unified format
- "nocommon" patches are in unified format but without common lines
- diffs are normal diff outputs, maybe more human-friendly

onepiece are recursive macropatches, handy for estimating the overall amount of changes; do not apply them "as is"

`only_jp` and `only_en` are lists of files which have only one version<br/>
`broken_en` is a list of invalid json files, check asap if it's not empty

all translatable lines are replaced with special string `#BELLA=key=SPINA#`, e.g. `#BELLA=textLeft=SPINA#` with no indentation<br/>
subdirectory names are numbers of special line occurrences, including common ones if any<br/>
`000` patches are more or less safe to apply directly, but the bigger the number (especially in nocommon) the more checking/editing is required

files in `valid` directory are successfully (0 hunk rejections, 0 special lines) patched scenarios which are still valid as json

# totes
jp scenarios: 5606<br/>
en scenarios: 3398<br/>
comparable files: 3378<br/>
broken files: 1<br/>
patches: 628<br/>
conflicts: 2458<br/>
valid results: 430
