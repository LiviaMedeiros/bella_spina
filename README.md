# bella_spina
magireco scenario patches

patching from translated ones to latest jp versions

### metadata patches
- `patches` are in unified format
- `"nocommon" patches` are in unified format but without common lines
- `diffs` are normal diff outputs, maybe more human-friendly
- `"sbs" diffs` are side-by-side without common lines, max width 150
- `rfc6902` are one-way json diffs

#### details
all translatable lines are replaced with special string `#BELLA=key=SPINA#`, e.g. `#BELLA=textLeft=SPINA#` with no indentation<br/>
subdirectory names are numbers of special line occurrences, including common ones if any<br/>
`000` patches are more or less safe to apply directly, but the bigger the number (especially in nocommon) the more checking/editing is required

### results
files in `/invalid/` directory are successfully (0 hunk rejections, 0 special lines) patched scenarios which are invalid as json<br/>
`/valid/` has ret-2-go minified scenarios

### /macro/
`onepiece` are recursive macropatches, handy for estimating the overall amount of changes; do not apply them "as is"

### /checkout/
- `broken`: list of invalid json files, check asap if it's not empty<br/>
- `bom`: list of files/lines containing `0xefbbbf` sequence<br/>
- `widelines`: lists of suspiciously long lines<br/>
- `escapism`: lists of files/lines/counts for all escape sequences except for `\"`

### extra analysis
- `/chars/`: all unique symbols separated by linebreak, and some diff data<br/>
- `/ambivalence/`: data for all translatable values with more than one translation<br/>
- `/inline/`: data for all changed inline [tags]<br/>
- `/stats/`: sorted patch statistics<br/>
- `/rerun/`: data about identical scenarios<br/>
- `/spellcheck/`: hunspell-related data<br/>
- `/escapism/`: all escape sequence occurrences

# totes
```asm
      0 broken_en
      0 bom_en
   6872 all_en
   8515 all_jp
   2992 all_na
   2727 same_na
    265 changed_na
     58 only_en
   1701 only_jp
   6814 comparable
     42 same
   5795 perfect
   1019 outdated
     13 invalid
    758 valid
```
```c
2404 onepiece-nocommon.patch
3744 onepiece-rfc6902.json
2244 onepiece-sbs.diff
2216 onepiece.diff
5296 onepiece.patch
```
