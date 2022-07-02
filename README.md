## Senior test task 

### Main task:
Your task is to create a UI element that can draw price charts
The chart can be scrolled left and right, and the candles should shrink and expand relative to the frame in which they are contained.
Use **UIKIT + SnapKit + StoryBoards** for screen layout

You can decompose this task into smaller ones, for example:
- Creating a web layer.
- Drawing a candle.
- Rendering of a non-interactive price chart.
- Adding price and time scales
- Adding a scrolling function.

If you have difficulties with any item, skip it and specify it in README.md what difficulties do you have with this and what possible solutions there may be.

### Use Design [Figma](https://www.figma.com/file/uVCfFE9Jylx3UteucIbH8i/Candlestick-Chart-Test?node-id=408%3A123).

![image](https://user-images.githubusercontent.com/29371921/175809761-263f4fc7-e918-4884-9ba6-5debb4a7b72d.png)

### Additional task №1:
In this task, you need to create a new screen with a list of currencies.
Clicking on a list item opens a screen with a graph. Make it possible to close this chart and choose a new currency.
Use "BTCUSDT", "LTCUSDT" and "ETHUSDT" for the list of currencies.
After selecting the currency, the application must make a new request with the selected currency to the exchange server in order to get the correct price data.

### Additional task №2:
Drawing events on the chart. event is a point on the chart.
In this task, you will need to use Cloud Firestore as a data store.
We suggest you use a data structure like this:

```
{
  "eventName": "Sell",
  "time": "1656758911",
  "price": "32800"
}
```

Use the time parameter to position the icon horizontally. The price parameter for the vertical position. Event name parameter for selecting the icon type.

Create a collection on the Cloud Firestore and several events that the application will be able to receive.

![image](https://user-images.githubusercontent.com/29371921/176998095-40deac07-f546-4b8d-a6c3-bd752a18b8e5.png)


![image](https://user-images.githubusercontent.com/29371921/175809836-08f29925-7ade-4e4a-a218-1aae0c377cd2.png)


### Additional task №3:
Use Firebase/Amplitude for analytics.
Use events for screen transitions, errors and crashes

### Task completion time:
1 day

### Acceptance conditions:
Repository on GitHub with completed test task
**Necessarily!** The README.md of the repository specifies:
Full description of the problem solution
List of completed tasks, as well as outstanding tasks and known bugs (if any)
Description of the difficulties encountered in the process
Decomposition: division into subtasks, their initial assessment and estimated execution time

### Basic development requirements:
Keep the UI as close to the layout as possible.
Use standard fonts, and take any suitable icons.
Don't get carried away! However, you still need to do it with the highest quality, as if this application will really go to the AppStore.
Don't Forget Error Handling and Load Status.
We want to see the code beautiful and without unnecessary garbage, according to the guidelines.
You can take any libraries, but remember that the more code you have, the better.
Publish the code on GitHub (by the way, we also look at the quality of git maintenance).

### To get an array of candlesticks for a chart. API:
```
https://fapi.binance.com/fapi/v1/klines?symbol=BTCUSDT&interval=15m&limit=100
```
**Parameters:**
- symbol: BTCUSDT, ETHUSDT, LTCUSDT
- interval: 15m, 30m, 1h
- limit: 100, 500, 1500

### Response:
```
[
  [
    1499040000000,      // Open time
    "0.01634790",       // Open
    "0.80000000",       // High
    "0.01575800",       // Low
    "0.01577100",       // Close
    "148976.11427815",  // Volume
    1499644799999,      // Close time
    "2434.19055334",    // Quote asset volume
    308,                // Number of trades
    "1756.87402397",    // Taker buy base asset volume
    "28.46694368",      // Taker buy quote asset volume
    "17928899.62484339" // Ignore.
  ]
]
```

![image](https://user-images.githubusercontent.com/29371921/175809851-7bf28f3d-f9be-40b3-9a65-e3ab535849ef.png)


