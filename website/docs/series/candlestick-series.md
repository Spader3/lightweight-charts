# Candlestick Series

A candlestick chart shows price movements in the form of candlesticks.

On the candlestick chart, open & close values form a solid body of a candle while wicks show high & low values for a candlestick's time interval.

![Candlestick chart example](/img/candlestick-series.png "Candlestick chart example")

## How to create candlestick series

```js
const candlestickSeries = chart.addCandlestickSeries();

// set data
candlestickSeries.setData([
    { time: '2018-12-19', open: 141.77, high: 170.39, low: 120.25, close: 145.72 },
    { time: '2018-12-20', open: 145.72, high: 147.99, low: 100.11, close: 108.19 },
    { time: '2018-12-21', open: 108.19, high: 118.43, low: 74.22, close: 75.16 },
    { time: '2018-12-22', open: 75.16, high: 82.84, low: 36.16, close: 45.72 },
    { time: '2018-12-23', open: 45.12, high: 53.90, low: 45.12, close: 48.09 },
    { time: '2018-12-24', open: 60.71, high: 60.71, low: 53.39, close: 59.29 },
    { time: '2018-12-25', open: 68.26, high: 68.26, low: 59.04, close: 60.50 },
    { time: '2018-12-26', open: 67.71, high: 105.85, low: 66.67, close: 91.04 },
    { time: '2018-12-27', open: 91.04, high: 121.40, low: 82.70, close: 111.40 },
    { time: '2018-12-28', open: 111.51, high: 142.83, low: 103.34, close: 131.25 },
    { time: '2018-12-29', open: 131.33, high: 151.17, low: 77.68, close: 96.43 },
    { time: '2018-12-30', open: 106.33, high: 110.20, low: 90.39, close: 98.10 },
    { time: '2018-12-31', open: 109.87, high: 114.69, low: 85.66, close: 111.26 },
]);
```

## Data format

Each item of the candlestick series is either an [OHLC](../data/ohlc.md) or a [whitespace](../data/whitespace-data.md) item.

## Customization

Colors for rising and falling candlesticks have to be set separately.

Candlestick borders and wicks are visible by default and may be disabled. Note that when wicks are disabled the candlestick doesn't show high and low price values.

Border and wick color can be either set for all candlesticks at once or for rising and falling candlesticks separately. If the latter is your preference please make sure that you don't use common options such as `borderColor` and `wickColor` since they have higher priority compared to the specific ones.

Candlestick series interface can be customized using the following set of options: [CandlestickStyleOptions](/api/interfaces/CandlestickStyleOptions).

### Examples

- set initial options for candlestick series:

    ```js
    const candlestickSeries = chart.addCandlestickSeries({
        upColor: '#6495ED',
        downColor: '#FF6347',
        borderVisible: false,
        wickVisible: true,
        borderColor: '#000000',
        wickColor: '#000000',
        borderUpColor: '#4682B4',
        borderDownColor: '#A52A2A',
        wickUpColor: '#4682B4',
        wickDownColor: '#A52A2A',
    });
    ```

- change options after series is created:

    ```js
    // for example, let's override up and down color of the candle
    candlestickSeries.applyOptions({
        upColor: 'rgba(255, 0, 0, 1)',
        downColor: 'rgba(0, 255, 0, 1)',
    });
    ```
