```jsx
{
 "clientCnt": {
    "dataFirstLabel": 1672531200000,
    "dataLastLabel": 1672534800000,
    "datas": [
      [
        [1672531200000, 100],
        [1672531500000, 150],
        [1672531800000, 120]
      ],
      [
        [1672531200000, 200],
        [1672531500000, 250],
        [1672531800000, 220]
      ]
    ],
    "lastLabel": 1672531800000,
    "minLabel": 1672531200000,
    "names": ["Queue_1", "Queue_2"],
    "threshold": [180, 250],
    "yMaxValue": [150, 250]
  },
  "pendMsgCnt": {
    "dataFirstLabel": 1672531200000,
    "dataLastLabel": 1672534800000,
    "datas": [
      [
        [1672531200000, 10],
        [1672531500000, 15],
        [1672531800000, 12]
      ]
    ],
    "lastLabel": 1672531800000,
    "minLabel": 1672531200000,
    "names": ["Pending_Queue"],
    "threshold": [20],
    "yMaxValue": [15]
  },
  "inMsgRate": {
    "dataFirstLabel": 1672531200000,
    "dataLastLabel": 1672534800000,
    "datas": [
      [
        [1672531200000, 300],
        [1672531500000, 320],
        [1672531800000, 310]
      ]
    ],
    "lastLabel": 1672531800000,
    "minLabel": 1672531200000,
    "names": ["In_Message_Rate"],
    "threshold": [400],
    "yMaxValue": [320]
  }
}

  
  const combinedColors = () => {
    if (chartType === "inMsgRate" || chartType === "inByteRate") {
      const outType = chartType === "inMsgRate" ? "outMsgRate" : "outByteRate";
      return [
        ...getDynamicColors(chartType, monitoringData[chartType]),
        ...getDynamicColors(outType, monitoringData[outType]),
      ];
    }

    return getDynamicColors(chartType, monitoringData[chartType]);
  };
```
