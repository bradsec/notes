## grep sed awk commands

Date:  Nov 1, 2022
Topics: [[grep]] [[sed]] [[awk]]  

---

#### Extract e-mail addresses using regular expression
`echo "goodemail@email.us bademail%email.com goodemail@email.co.uk bademail@com" | grep -E -o "\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,6}\b"`

*Result:*
```
goodemail@email.us
goodemail@email.co.uk
```

#### Remove all but alpha numeric characters from a string using sed
`echo "123%@#$ a b c" | sed 's/[^a-zA-Z0-9]//g'`

*Result:*
```
123abc
```

#### Extract unique hex colour codes using grep
`echo "colors #000000, #111111, #111111, #222222"  | grep -Po "#[0-9a-f]{6}" | sort | uniq`

*Result:*
```
#000000
#111111
#222222
```
