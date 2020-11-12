# stop-watch
Stop-watch without using date command in bash

```
#!/bin/bash

set -e


i=00;

for i in $(seq -f %02g 0 24);
do
	j=00
	if [[ $i == 24 ]];then break; fi
	for j in $(seq -f %02g 0 60);
	do
		k=00
		if [[ $j == 60 ]];then break; fi
		for k in $(seq -f %02g 0 60);
		do
			m=000
			if [[ $k == 60 ]];then break; fi
			for m in $(seq -f %03g 0 100);
			do
				sleep 0.01;
				
				if [[ $m == 100 ]];then break; else clear && echo -e "\n \e[1;42m \033[1m $i:$j:$k:$m \033[00m \e[0m \n"; fi
			done
		done
	done
done
```
