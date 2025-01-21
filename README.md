#!/bin/bash

files="*.c *.h */*.c */*.h"
file_count=$(find $files -type f | wc -l)
norme_count=$(norminette | wc -l)

if [ "$file_count" -ne "$norme_count" ]; then
    diff=($norme_count - $file_count)
    echo -e "\n\033[31;1;4mPossibili $diff errori di norma!\033[0m\n"
    git push $@
    exit 1
fi
    git push $@	
exit 0
