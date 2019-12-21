# 1266. Minimum Time Visiting All Points
Easy

On a plane there are n points with integer coordinates points[i] = [xi, yi]. Your task is to find the minimum time in seconds to visit all points.

You can move according to the next rules:

    In one second always you can either move vertically, horizontally by one unit or diagonally (it means to move one unit vertically and one unit horizontally in one second).
    You have to visit the points in the same order as they appear in the array.

 

Example 1:

Input: points = [[1,1],[3,4],[-1,0]]
Output: 7
Explanation: One optimal path is [1,1] -> [2,2] -> [3,3] -> [3,4] -> [2,3] -> [1,2] -> [0,1] -> [-1,0]   
Time from [1,1] to [3,4] = 3 seconds 
Time from [3,4] to [-1,0] = 4 seconds
Total time = 7 seconds

Example 2:

Input: points = [[3,2],[-2,2]]
Output: 5

 

Constraints:

    points.length == n
    1 <= n <= 100
    points[i].length == 2
    -1000 <= points[i][0], points[i][1] <= 1000


---
#### Runtime: 52 ms, faster than 94.84% of JavaScript online submissions for Minimum Time Visiting All Points.
#### Memory Usage: 35.6 MB, less than 100.00% of JavaScript online submissions for Minimum Time Visiting All Points.
```javascript
var minTimeToVisitAllPoints = function(points) {
    let time = 0;
    let x = 0;
    let y = 0;
    let z = 0;
    let w = 0;
    for(let i=0; i<points.length-1; i++){
        [x, y] = points[i+1];
        [z, w] = points[i];
        time += Math.max(Math.abs(z - x), Math.abs(w - y));
    }
    return time;
};
```

## Declaring 4 variables has same runtime as calling specific points in array directly

#### Runtime: 56 ms, faster than 86.92% of JavaScript online submissions for Minimum Time Visiting All Points.
#### Memory Usage: 34.8 MB, less than 100.00% of JavaScript online submissions for Minimum Time Visiting All Points.

```javascript
var minTimeToVisitAllPoints = function(points) {
    let time = 0;
    for(let i=0; i<points.length-1; i++){
        time += Math.max(Math.abs(points[i][0] - points[i+1][0]), Math.abs(points[i][1] - points[i+1][1]));
    }
    return time;
};
```

---
#### Runtime: 64 ms, faster than 42.52% of JavaScript online submissions for Minimum Time Visiting All Points.
#### Memory Usage: 34.8 MB, less than 100.00% of JavaScript online submissions for Minimum Time Visiting All Points.
```javascript
var minTimeToVisitAllPoints = function(points) {
    return points.reduce((data, item) => {
        if(data.temp === 0){
            data.temp = item;
        } else {
            data.total += Math.max(Math.abs(data.temp[0] - item[0]), Math.abs(data.temp[1] - item[1]));
            data.temp = item;
        }
        return data;
    }, {total: 0, temp: 0}).total
};
```
