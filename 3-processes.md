# 3 Processes

```bash
if [ -z $1 ]
then
	echo "No paramms"
	exit
else 
 	if ps | grep -q $1
 		then
 		echo "Process $1 is running"
 	else
 		echo "Process $1 isn't running"
	fi
fi
```

