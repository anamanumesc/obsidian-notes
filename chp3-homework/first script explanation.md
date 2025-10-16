Create a script that will go through all the files in /work/files/wiki/ and count the occurance of engineer. The output needs to have both the number of occurances and the time the script needed to find the solution

```bash
#!/usr/bin/env bash

start=$(date +%s)
total=0

for f in $(find /work/files/wiki/ -type f); do
  c=$(grep -i -o 'engineer' "$f" | wc -l) 
  total=$((total + c))
done

end=$(date +%s)
echo "occurrences: $total"
echo "time: $((end - start))s"

```

