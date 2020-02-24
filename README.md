# crazyObservable

crazyObservable is a custom rxjs observable that is used as a blueprint to a stream of data drawn from *all possibilities* of emmiting a predefined number emissions over a fixed discrete time period. Thisobservable is intended to give a better approach to tackle problems like described in those questions:

  * https://stackoverflow.com/questions/35060681/rxjs-how-can-i-generate-a-stream-of-numbers-at-random-intervals-within-a-speci
  * https://stackoverflow.com/questions/41628268/observable-that-delays-a-random-time-everytime-the-stream-ends/41632041#41632041
  * https://stackoverflow.com/questions/41388199/how-to-create-an-infinite-observable-that-produces-random-numbers-at-random-inte/41393512
  
 The following Marble diagram shows a possible datastream obtained by a subscription to crazyObservable(16, 1000, 7) where 16 is the totalNumberOfEmissions, 1000 is the timeInterval (in milliseconds) and 7 is the totalNumberOfTimeIntervals.

![Marble diagram of brazyObservable](./crazyObservableMarbleDiagram.png)

The following code gives an example of how to use crazyObservables.

```
var oneHourRandomTenHundredRequisition$ = crazyObservable(10000, 1000, 60 * 60);
// crazyObservable( totalNumberOfEmissions, timeInterval (miliseconds), totalNumberOfTimeIntervals )

let testComponent1 = oneHourRandomTenHundredRequisition$.subscribe({
next() { console.log("That's up to you!"); } ,
error() { console.log("An error have been encountered."); },
complete() { console.log("crazyObservable is garanteed to complete, unless your custom next() return an error}
});
```

I will soon upload a for crazyObservable validity that relies in the *discrete random assignment* implemented [here](./discreteRandomAssignment.js). I am also up to refactoring this code to serve as a singleton service for Angular apps as soon as possible.



  
