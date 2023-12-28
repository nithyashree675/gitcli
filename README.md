# gitcli

**List commits over an year** 
```
git log  --sparse --oneline --no-notes --since="1 year ago" > gitlog.txt
```

**List files changed in the commits over an year**
```
cat gitlog.txt  | cut -d' ' -f 1 | xargs -I{} git diff-tree --no-commit-id --name-only -r {} > files-changed.txt
cat files-changed.txt | sort | uniq
```
