---
#### Runtime: 52 ms, faster than 83.58% of JavaScript online submissions for Distance Between Bus Stops.
#### Memory Usage: 34.8 MB, less than 100.00% of JavaScript online submissions for Distance Between Bus Stops.
```javascript
var distanceBetweenBusStops = function(distance, start, destination) {
    const result = [0, 0];
    const arr = distance.slice();
 
    if(start > destination){
        arr.splice(destination, Math.abs(start-destination));
        for(let i=destination; i<start; i++){
            result[1] += distance[i];
        }
        
        for(let i=0; i<arr.length; i++){
            result[0]  += arr[i];
        }
    } else {
        arr.splice(start, Math.abs(start-destination));
        for(let i=start; i<destination; i++){
            result[1] += distance[i];
        }
        for(let i=0; i<arr.length; i++){
            result[0]  += arr[i];
        }
    }
    return Math.min(...result);
};
```
