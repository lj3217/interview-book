### echarts按需引入大全

```javascript
require('echarts/lib/chart/line')

require('echarts/lib/chart/bar')

require('echarts/lib/chart/pie')

require('echarts/lib/chart/scatter')

require('echarts/lib/chart/radar')

require('echarts/lib/chart/map') // 地图

require('echarts/lib/chart/treemap')

require('echarts/lib/chart/graph')

require('echarts/lib/chart/gauge')

require('echarts/lib/chart/funnel')

require('echarts/lib/chart/parallel')

require('echarts/lib/chart/sankey')

require('echarts/lib/chart/boxplot')

require('echarts/lib/chart/candlestick')

require('echarts/lib/chart/effectScatter')

require('echarts/lib/chart/lines')

require('echarts/lib/chart/heatmap')

require('echarts/lib/component/graphic')

require('echarts/lib/component/grid')

require('echarts/lib/component/legend') // 图例

require('echarts/lib/component/tooltip')

require('echarts/lib/component/polar')

require('echarts/lib/component/geo')

require('echarts/lib/component/parallel')

require('echarts/lib/component/singleAxis')

require('echarts/lib/component/brush')

require('echarts/lib/component/title') // 标题

require('echarts/lib/component/dataZoom')

require('echarts/lib/component/visualMap') // 视觉映射

require('echarts/lib/component/markPoint')

require('echarts/lib/component/markLine')

require('echarts/lib/component/markArea')

require('echarts/lib/component/timeline')

require('echarts/lib/component/toolbox')

require('zrender/lib/vml/vml')
```

### Echarts自适应失效 

```javascript
Echarts自适应失效  window.onresize；或者多个图标使用时只有最后一个图标生效
这是可以使用：
window.addEvenListener("resize", function () {
	myChart.resize()
})
```

