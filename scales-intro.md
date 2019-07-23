
# scales

scales can be divided into three categories:


### 1. scales with continuous input and continuous output
```
const linearScale = d3.scaleLinear()
  .domain([0.1, 1])
  .range([0, 600]);

linearScale(0.1);   // returns 0
linearScale(0.55);   // returns 300
linearScale(1);  // returns 600
```

![](https://i.imgur.com/sIpt1AV.png)



### 2. scales with discrete input and discrete output


```
const myData = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']

const ordinalScale = d3.scaleOrdinal()
  .domain(myData)
  .range(['black', 'grey', 'grey']);

ordinalScale('Jan');  // returns 'black';
ordinalScale('Feb');  // returns 'grey';
ordinalScale('Mar');  // returns 'grey';
ordinalScale('Apr');  // returns 'black';
```


![](https://i.imgur.com/f7Dh55h.png)



### 3. scales with continuous input and discrete output
```
const quantizeScale = d3.scaleQuantize()
  .domain([0, 100])
  .range(['lightblue', 'orange', 'lightgreen', 'pink']);

quantizeScale(10);   // returns 'lightblue' because it is the first quarter of the domain value
quantizeScale(30);  // returns 'orange' because its in the second quarter
quantizeScale(90);  // returns 'pink' because its in the fourth quarter
```
![](https://i.imgur.com/IcrBSdX.png)

### Most common scales

Most common scales fit into the first two categories above.

for type one you need to ask if the continuous data is time or numbers, if it is time it is likely to use 
```
d3.scaleTime()
```
if it isnt time, and is numbers it is most likely to use 
```
d3.scaleLinear()
```

for type two the most common scale is 
```
d3.scaleOrdinal()
```
