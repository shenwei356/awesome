- [How do I use a Bash variable (string) containing quotes in a command?](https://superuser.com/questions/360966/how-do-i-use-a-bash-variable-string-containing-quotes-in-a-command)

        outfmt=("6 qseqid sseqid pident")
        blastn ... -outfmt "${outfmt[@]}" 
