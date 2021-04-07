```
#swap usage
for pid in $(ps -ef | grep -i java| grep -v grep|awk '{print $2}')
do
for file in /proc/${pid}/status 
do 
awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $file;
ps -ef | grep -i ${pid}|grep -v grep
done
done
```

