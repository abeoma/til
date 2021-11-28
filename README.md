# til

## Replace a specific string in a directory/file name
```
# Show directories and files that contain "hoo" in their name
find . -name '*hoo*'

# Replace "hoo" with "bar"
find . -name '*hoo*' | sed 'p;s/hoo/bar/' | xargs -n2 mv
```

## Replace a specific string in a file
```
# Show lines containing the string "hoo"
find . -type f | xargs grep "hoo"

# Replace "hoo" with "bar"
find . -type f | xargs -0 sed -i '' 's/hoge/fuga/g'

# If error occured: File name too long
find . -type f | xargs -n 10 sed -i '' 's/hoge/fuga/g'
```
