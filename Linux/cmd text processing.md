

echo "smt" > /dev/stdout

- prints text to standard output (screen)
    

echo "smt" > /dev/stderr

- prints text to standard error (error stream)
    
- echo = display line of text
    

grep, wc, sed, awk, xargs  
grep = global regular expression print, search text  
wc = word count (lines, words, bytes)  
sed = stream editor, used for find and replace  
awk = named after authors (Aho, Weinberger, Kernighan), text processor by columns  
xargs = execute command using input as arguments

symbol meanings (safe for obsidian):  
(redirect output) -> overwrite  
(append output) -> add to file  
(read input) -> take input from file  
(read until delimiter) -> multiline input  
(pipe) -> send output to another command  
(redirect stdout+stderr) -> combine both outputs  
(stderr to stdout) -> send error to same place as output

sed -i 's/ops/devops/g' file.out

- replaces "ops" with "devops" in file
    
- -i = in-place edit
    
- s = substitute
    
- g = global (all matches)
    

cat file.out | awk '{ print $3 }'

- prints 3rd column of each line
    

ls -al | awk '{ print $1,$4 }'

- prints 1st and 4th columns (permissions and owner)
    

cat file.ou3 2> err.file.out 1> file.out

- send normal output to file.out, errors to err.file.out
    

cat file.ou3 >> file.out 2>&1

- append both stdout and stderr to file.out
    

ls -al | tee -a file.out

- show output and append to file.out simultaneously
    
- tee = named after T-split pipe, writes to file and screen
