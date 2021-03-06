<h2>Candle.js</h2>
<p>
Candle.js 는 캔들차트를 그리기 위한 라이브러리입니다.<br/>
캔들차트가 주고, 보조지표에 필요한 다른 차트타입도 사용할 수 있습니다.
</p>

<p>
지금까지 캔들차트는 다른 차트라이브러리의 부가적인 기능으로 딸려오는 경우가 많았습니다.<br/>
이는 캔들차트를 위해 필요없는 로직들을 불러오고,<br/>
대부분의 라이브러리들이 svg 방식으로 구현되어있다는 점 때문에 너무 많은 자원낭비와 속도저하를 야기했습니다.<br/>
(캔들차트와 같이 데이터량이 많은 차트를 svg로 그릴경우 심각한 속도저하가 일어납니다.)<br/>
</p>

<p><b>반면 candle.js는 앞서 설명한 문제점들을 모두 개선했습니다.</b></p>
  
<p>
덭붙혀 candle.js의 개발지향점은 다음과 같습니다.
<ol>
  <li>
    <b>속도와 용량이 가벼워야한다.</b>
    <ul>
      <li>DOM , SVG 출력을 하지 않는다.</li>
      <li>사용자에게 너무 많은 자유도를 주지않는다.</li>
      <li>사용자의 입력값에 대한 타입,형식체크를 지양한다.</li>
    </ul>
  </li>
  <li>
    <b>빌드환경이 가벼워야 한다.</b>
  </li>
</ol>
</p>

<h2>Examples</h2>

```js
const chart = new Chart('stock-board');

chart.setTimeline(data.map(item => item.CreateTime));
chart.addLayer(
  'layerName',
  {
      type: 'candle',
      data: data.map(
        item => ({
            open: item.OpenPrice,
            close: item.ClosePrice,
            high: item.HighPrice,
            low: item.LowPrice
        })
      )
  }
);

chart.render();
```

<h2>Architecture</h2>
<p><img src="http://i.imgur.com/HgV42pc.png"/></p>
