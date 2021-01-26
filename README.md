# bella_spina
magireco scenario patches

patching from translated ones to latest jp versions

- patches are in unified format
- "nocommon" patches are in unified format but without common lines
- diffs are normal diff outputs, maybe more human-friendly

onepiece are recursive macropatches, handy for estimating the overall amount of changes; do not apply them "as is"

`broken_en` is a list of invalid json files, check asap if it's not empty<br/>
`bom_en` is a list of files/lines containing 0xefbbbf sequence

all translatable lines are replaced with special string `#BELLA=key=SPINA#`, e.g. `#BELLA=textLeft=SPINA#` with no indentation<br/>
subdirectory names are numbers of special line occurrences, including common ones if any<br/>
`000` patches are more or less safe to apply directly, but the bigger the number (especially in nocommon) the more checking/editing is required

files in `valid` directory are successfully (0 hunk rejections, 0 special lines) patched scenarios which are still valid as json

# totes
```
     0 broken_en
  3536 all_en
  5620 all_jp
    67 only_en
  2151 only_jp
  3469 comparable
  2839 perfect
   630 outdated
   430 valid
```
