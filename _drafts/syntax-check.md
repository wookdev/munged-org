---
comments: true
title: Code Fences and Syntax Highlighting
excerpt: What happens whith code fences
---

This is a code fence, set to javascript:

```javascript
let objToStringIfy = {"prop":"value"};
const testJsonString = JSON.stringify( objToStringIfy )
```

Some bash:

```shell
#!/bin/bash

exdir=$(dirname $0)
pfx=$(mktemp -d /tmp/$(basename $0).XXXXXXXXXX) || exit 1

for sourcefile in *.md
do

    # yeah, I could have done this way better, but "cut" is what I could remember
    id=$(echo ${sourcefile} | cut -d '.' -f 1 | cut -d '-' -f 4- | egrep '^[0-9]+' );

    if [ -n "${id}" ]; then
    
        tmpfile=${pfx}/${sourcefile}
        cp ${sourcefile} ${tmpfile}
        
        echo $id $tmpfile $sourcefile

        awk -v id=$id -f ${exdir}/addid.awk $tmpfile > $sourcefile

    fi
done

exit 0
```

And some awk:

```awk
# pass 'id' in via the -v switch on the awk command line
#
/---/ && NR > 1 \
    {
        printf "mtid: %d\n", id
        printf "redirect_from:\n"
        printf "  - /saga/%d.html\n", id
    }
# print all lines
    { print $0 }
```
