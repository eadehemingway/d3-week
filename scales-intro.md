
# scales

scales can be divided into three categories:


### 1. Continuous Input and Continuous Output
E.g graphs like line graphs or scatter graphs
```
const linearScale = d3.scaleLinear()
  .domain([0, 50])
  .range([0, 600]);

linearScale(0);   // returns 0
linearScale(25);   // returns 300
linearScale(50);  // returns 600
```

![](https://i.imgur.com/bF7yc3l.png)





### 2. Discrete Input and Discrete Output

E.g. most commonly used with bar graphs. 

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



### 3. Continuous Input and Discrete Iutput
```
const quantizeScale = d3.scaleQuantize()
  .domain([0, 100])
  .range(['lightblue', 'orange', 'lightgreen', 'pink']);

quantizeScale(10);   // returns 'lightblue' because it is the first quarter of the domain value
quantizeScale(30);  // returns 'orange' because its in the second quarter
quantizeScale(90);  // returns 'pink' because its in the fourth quarter
```
![](https://i.imgur.com/IcrBSdX.png)

## Most common scales

Most common scales fit into the first two categories above

#### Continuous Input and Continuous Output
with Continuous Input and Continuous Output you need to ask if the continuous data is time or numbers, if it is time it is likely to use `d3.scaleTime()` . If it isnt time, and is numbers it is most likely to use `d3.scaleLinear()`
#### Discrete Input and Discrete Output
for type two the most common scale is `d3.scaleOrdinal()`


### Further reading
https://github.com/d3/d3-scale
