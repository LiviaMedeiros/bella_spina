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
     1 bom_en
  5192 all_en
  6686 all_jp
  2992 all_na
  2814 same_na
   178 changed_na
     7 only_en
  1501 only_jp
  5185 comparable
    40 same
  4221 perfect
   964 outdated
    14 invalid
   706 valid
```
```c
1764 onepiece-nocommon.patch
3404 onepiece-rfc6902.json
1704 onepiece-sbs.diff
1596 onepiece.diff
3568 onepiece.patch
```
