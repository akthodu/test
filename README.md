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

```
####AWK Usage###
#Add  all rows in column2
cat $file|awk '{sum=sum+$2}END{print sum}'

#Print columns if column matches String
cat $file|awk '($3=="ERROR") {print $0}'

#Print columns if the column value is above.
cat $file|awk '($5>0) {print $0}'


#Sort bycolumn --numbericsort
cat $file|sort -n -k2

```
###Internal threads using top command. sort internal threads by cpu
top -c -p 125942 -H -b -n 1
```



