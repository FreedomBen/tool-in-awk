# tool-in-awk

You don't need `<common-tool>` because you can use `awk`!

## cat

Still using `cat` when `awk` is so much more 1337?

Instead of:

```bash
cat *.txt
```

Use:

```bash
awk '{ print }' *.txt
```

## grep

Instead of:

```bash
grep -E '<your regex>' *.txt
# or
some_command | grep -E '<your regex>'
```

Use:

```bash
awk '/<your regex>/' *.txt
# or
some_command | awk '/<your regex>/'
```

## sed

Instead of:

```bash
sed -E 's/<your regex>/your replacment/g' *.txt
# or
some_command | sed -E 's/<your regex>/your replacment/g' *.txt
```

Use:

```bash
awk '{ gsub(/command/, "shamand"); print }' *.txt
# or
some_command | awk '{ gsub(/command/, "shamand"); print }'
```

## wc

Instead of:

```bash
wc myfile.txt
```

Use:

```bash
awk '{ w += NF; c += length + 1 }; END {print NR, w, c, FILENAME }' myfile.txt
```

Way easier!

## Conclusion

Use the best tool for the job, and in every possible case, that best tool is `awk`.
