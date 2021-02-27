# bella_spina
magireco scenario patches

patching from translated ones to latest jp versions

- patches are in unified format
- "nocommon" patches are in unified format but without common lines
- diffs are normal diff outputs, maybe more human-friendly
- "sbs" diffs are side-by-side without common lines, max width 150

`onepiece` are recursive macropatches, handy for estimating the overall amount of changes; do not apply them "as is"

`broken_en` is a list of invalid json files, check asap if it's not empty<br/>
`bom_en` is a list of files/lines containing 0xefbbbf sequence<br/>
`widelines_en` is a list of suspiciously long lines

`chars` files have all unique symbols separated by linebreak, and some diff data<br/>
`ambivalence` has data for all translatable values with more than one translation<br/>
`inline` has data for all changed inline [tags]

all translatable lines are replaced with special string `#BELLA=key=SPINA#`, e.g. `#BELLA=textLeft=SPINA#` with no indentation<br/>
subdirectory names are numbers of special line occurrences, including common ones if any<br/>
`000` patches are more or less safe to apply directly, but the bigger the number (especially in nocommon) the more checking/editing is required

files in `valid` directory are successfully (0 hunk rejections, 0 special lines) patched scenarios which are still valid as json

# totes
```asm
     0 broken_en
    25 bom_en
  3792 all_en
  5893 all_jp
  2992 all_na
     8 only_en
  2109 only_jp
  3784 comparable
    32 same
  3201 perfect
   583 outdated
   378 valid
```
