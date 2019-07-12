# 4 File Diff

```bash
if [ $# -ne 2 ]; then
	
	echo "Please give two files as parameter"
	exit
fi

if [ $(sed $= -n $1) -gt $(sed $= -n $2) ]; then
	big=$1
	small=$2

else
	big=$2
	small=$1
fi

anzBig=$(sed $= -n $big)
anzSmall=$(sed $= -n $small)

for (( i=1; i<=$anzBig; i=i+1 )); do
	
	lineBig=$(head -n $i $big | tail -n 1)

	if [ $i -gt $anzSmall ]; then
		
		echo "Datei 1: $lineBig"
		echo "Datei 2:  "
		echo "____"

		continue
	fi
	lineSmall=$(head -n $i $small | tail -n 1)

	if [ "$lineBig" == "$lineSmall" ]; then
		echo "No difference"
		echo "____"
	else
		echo "File 1: $lineBig"
		echo "File 2: $lineSmall"
		echo "____"
	fi
done
```

