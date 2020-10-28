# 場景
THREE.Scene()

## 增加對象 / 移除對象
* 增加對象：add(object)
* 移除對象：remove(object)
* 獲取對象列表，包含攝影機及光源（陣列型態）：children()
* 透過對象名字取得特定對象：getObjectByName(name, recursive)
* 對象數量：children.length
* 遍歷該對象及其後代：traverse(function)

## 霧化效果
場景的fog屬性可以加上霧化效果，場景中的對象越遠就越模糊。有以下兩種class可使用。
* THREE.Fog(color, near, far): 可自訂模糊範圍，霧的濃度是線性增長。
* THREE.FogExp2(color, density): 隨著距離承指數增長。

## 材質覆蓋
場景的overrideMaterial屬性如果不為null，可以讓場景中的物件強制覆蓋為此屬性指向的材質。