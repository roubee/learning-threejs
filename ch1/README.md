Three.js是一個Javascript 3D library，可以讓使用者更易於操作WebGL渲染3D繪圖，除了預設的WebGL它也提供CSS2、SVG及CSS3D等renderer。

## 瀏覽器支援度
目前主流瀏覽器皆有支援WebGL，參考[官方文件](https://threejs.org/docs/#manual/en/introduction/Browser-support)。
* Google Chrome 9+
* Firefox 4+
* Opera 15+
* Safari 5.1+
* Internet Explorer 11
* Microsoft Edge

## 三維空間
Three.js採用右手座標系統（right handed coordinate system）。如果將右手大拇指伸出、食指向上、中指向前，則大拇指為X軸、食指為Y軸、中指為Z軸。在Three.js的軸中分別以紅色、綠色、藍色區分。

## 材質
MeshBasicMaterial(): 只會依照給予的顏色渲染物體（平面或線框），並不會對光源有反應。  
MeshLambertMaterial(): 會對光源有反應。  
MeshPhongMaterial(): 會對光源有反應。

## 陰影
由於渲染陰影需要大量的計算，所以Three.js默認不會渲染陰影。須透過以下方法設定。
1. 設定渲染器的shadowMap.enabled屬性來開啟。以及設定shadowMap.type，分為以下三種，PCFSoftShadowMap的陰影最圓滑。
  * THREE.BasicShadowMap = 0
  * THREE.PCFShadowMap = 1
  * THREE.PCFSoftShadowMap = 2
2. 設定物件的receiveShadow屬性為接受陰影，或是設定castShadow為投射陰影。
3. 設定可以產生陰影的光源（SpotLight物件）的receiveShadow屬性。

## 動畫
比起setTimeout()或setInterval()，使用requestAnimationFrame()實現動畫可防止掉幀提升效能。且當該頁面處於背景狀態（例如切換到別的分頁），瀏覽器會暫停呼叫requestAnimationFrame()。待頁面被啟用時，動畫會從上次停止的地方繼續執行。關於requestAnimationFrame()可參閱這個文章的介紹：[你知道的requestAnimationFrame【从0到0.1】](https://juejin.im/post/6844903761102536718)。

#### 動畫幀數
使用[stats.js](https://github.com/mrdoob/stats.js)這個library可以檢測動畫幀數（fps），即一秒的幀數。