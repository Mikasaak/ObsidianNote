---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
oldVNode和newVNode是否通过sameVNode函数比较是true ^yTWgNmcS

是DOM节点 ^0FSh5Hdf

是虚拟节点 ^V0hEtnwb

调用patchVNode精细化比较 ^PE8cBTxy

patch(oldVNode,newVNode)函数被调用 ^6J4sIFIs

判断oldVNode是虚拟节点还是DOM节点 ^9aaSFL8k

将oldVNode包装为虚拟节点 ^R3yXPWxQ

删除旧节点，插入新节点 ^lhIJq99b

否 ^2sLhlbZP

是 ^Y9T2iNrY

oldVNode和newVNode是否在内存中是同一对象 ^M5i1DTDP

不做处理，直接返回 ^1UmnWtpI

是 ^n3ULmmol

newVNode是否有text属性 ^b26x0XoP

否 ^PZKjihkq

newVNode的text与oldVNode中text比较 ^2n3odB4B

是 ^EZQIk8J1

不做处理 ^9Zcd5rwd

将elm中的innerText属性改变为newVNode中的text属性值
（oldVNode中有chilrden属性也没事，因为innerText属性改变后，原来的chilrden也没了） ^dsWcXqXc

相同 ^K8PenjuR

不同 ^0yol8M2O

new和old是否都有chilrden属性 ^QWiMU5Jn

没有（意味着newVNode有chilrden属性） ^s1AlTSRL

只有旧节点有子节点而新节点没有，说明更新后的页面，旧节点全部都不见了，那么要做的，就是把所有的旧节点删除，也就是直接把`DOM` 删除 ^ReynsXh0

只有newVNode有子节点 ^yD18Jcih

只有oldVNode有子节点 ^0dgqDYJf

两者都有子节点 ^RvDMsRJ5

进行子节点更新，运行updateChildren函数 ^1lK8Mnak

只有新节点有子节点，旧节点没有，那么不用比较了，所有节点都是全新的，所以直接全部新建就好了，新建是指创建出所有新`DOM`，并且添加进父节点 ^Cj2B3beh

进行子节点数组的diff算法 ^gGk2R2dE

新头与旧头节点比较 ^qDZAtQDB

新尾与旧尾节点比较 ^oSK0pYdM

新尾与旧头节点比较 ^DacHb4Gi

新头与旧尾节点 比较 ^fXI9wyfA

不相似 ^ddaz5dtM

不相似 ^xEHlCyJm

不相似 ^ZKgQhXHu

newStartVnode
节点有key且在旧子节点数组中找到sameVnode ^ksfRA2eu

不相似 ^hA9OqVxr

相似 ^0znJ6tL6

相似 ^SWiYhJS1

相似 ^IMKoB1sX

相似 ^lJo7BBXU

进入下一次循环 ^56zKTE3V

直接 `patchVnode` ，同时新老 `VNode` 节点的开始索引都加 1 ^mscBUIGC

同样直接 `patchVnode` ，同时新老 `VNode` 节点的结束索引都减 1 ^a7O2LOdB

在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldEndVnode` 的后面，同时老 `VNode` 节点开始索引加 1，新 `VNode` 节点的结束索引减 1 ^5UBQtEGh

在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldStartVnode` 的前面，同时老 `VNode` 节点结束索引减 1，新 `VNode` 节点的开始索引加 1 ^ighKJXn7

条件成立 ^9qkzUrXA

不成立 ^xuowh7f9

调用 `createElm` 创建一个新的 `dom` 节点放到`oldStartVnode` 对应的真实 `dom` 的前面
 ^LLpAXavq

进行`patchVnode`，同时将这个真实 `dom`移动到 `oldStartVnode` 对应的真实 `dom` 的前面 ^qIfezPdv

while(oldStart <= oldEnd && newStart >= newEnd) ^3nuobmKi

条件成立进入循环 ^9StmYUsd

条件不成立 ^5RgQXZCq

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.25",
	"elements": [
		{
			"type": "arrow",
			"version": 2819,
			"versionNonce": 325719583,
			"isDeleted": false,
			"id": "1YhHtq18NzqWSJ9DJCiio",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -212.6037264377373,
			"y": -497.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.1584130089458426,
			"height": 85.74728734742507,
			"seed": 1133229539,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643742,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oLIPfTWtKpVKEJPDyOzis",
				"gap": 4,
				"focus": -0.09113744114380642
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.1584130089458426,
					85.74728734742507
				]
			]
		},
		{
			"type": "rectangle",
			"version": 961,
			"versionNonce": 1247487427,
			"isDeleted": false,
			"id": "oLIPfTWtKpVKEJPDyOzis",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -358,
			"y": -605.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 265,
			"height": 103.99999999999999,
			"seed": 79284717,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "6J4sIFIs"
				},
				{
					"id": "1YhHtq18NzqWSJ9DJCiio",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 367,
			"versionNonce": 2024098797,
			"isDeleted": false,
			"id": "6J4sIFIs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -349.51988983154297,
			"y": -578.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 248.03977966308594,
			"height": 50,
			"seed": 908665699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "patch(oldVNode,newVNode)\n函数被调用",
			"rawText": "patch(oldVNode,newVNode)函数被调用",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "oLIPfTWtKpVKEJPDyOzis",
			"originalText": "patch(oldVNode,newVNode)函数被调用",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "diamond",
			"version": 2173,
			"versionNonce": 1209496931,
			"isDeleted": false,
			"id": "VpiaaRtl8jXeISvEeeOU1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -395,
			"y": -416.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 368,
			"height": 170,
			"seed": 989855245,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9aaSFL8k"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 340,
			"versionNonce": 2135901773,
			"isDeleted": false,
			"id": "9aaSFL8k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -293.71998596191406,
			"y": -368.6171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165.43997192382812,
			"height": 75,
			"seed": 994844141,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "判断oldVNode是虚\n拟节点还是DOM节\n点",
			"rawText": "判断oldVNode是虚拟节点还是DOM节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "VpiaaRtl8jXeISvEeeOU1",
			"originalText": "判断oldVNode是虚拟节点还是DOM节点",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 225,
			"versionNonce": 1424544003,
			"isDeleted": false,
			"id": "Sxac85I_JoS6IaRnMtP4-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 129,
			"y": -362.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 299,
			"height": 83,
			"seed": 1379661197,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "LAR6GjsxJX8GMlKKBUrPJ",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "R3yXPWxQ"
				},
				{
					"id": "-1Ot4XSRZWw53PDqCwbNY",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 1737159853,
			"isDeleted": false,
			"id": "R3yXPWxQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 156.33003997802734,
			"y": -333.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.3399200439453,
			"height": 25,
			"seed": 376897677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "将oldVNode包装为虚拟节点",
			"rawText": "将oldVNode包装为虚拟节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Sxac85I_JoS6IaRnMtP4-",
			"originalText": "将oldVNode包装为虚拟节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1633,
			"versionNonce": 1528822335,
			"isDeleted": false,
			"id": "LAR6GjsxJX8GMlKKBUrPJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39.239545006484285,
			"y": -325.90852922789304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.2395450064843,
			"height": 14.328006266474574,
			"seed": 1876239405,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0FSh5Hdf"
				}
			],
			"updated": 1712543643745,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Sxac85I_JoS6IaRnMtP4-",
				"gap": 5.000000000000028,
				"focus": -0.413707963304932
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					163.2395450064843,
					14.328006266474574
				]
			]
		},
		{
			"type": "text",
			"version": 26,
			"versionNonce": 2097272589,
			"isDeleted": false,
			"id": "0FSh5Hdf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.219985961914055,
			"y": -325.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.43997192382812,
			"height": 25,
			"seed": 1903761933,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "是DOM节点",
			"rawText": "是DOM节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LAR6GjsxJX8GMlKKBUrPJ",
			"originalText": "是DOM节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 908,
			"versionNonce": 771009603,
			"isDeleted": false,
			"id": "1BWujxaz4DveoGHQCwHx2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -405,
			"y": -146.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387,
			"height": 170,
			"seed": 898500099,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yTWgNmcS"
				},
				{
					"id": "vMi0xNBvaN6lk2OafFoaj",
					"type": "arrow"
				},
				{
					"id": "-1Ot4XSRZWw53PDqCwbNY",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 438,
			"versionNonce": 1512926573,
			"isDeleted": false,
			"id": "yTWgNmcS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -302.48992919921875,
			"y": -98.6171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.4798583984375,
			"height": 75,
			"seed": 1664419587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "oldVNode和newVNod\ne是否通过sameVNo\nde函数比较是true",
			"rawText": "oldVNode和newVNode是否通过sameVNode函数比较是true",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "1BWujxaz4DveoGHQCwHx2",
			"originalText": "oldVNode和newVNode是否通过sameVNode函数比较是true",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 386,
			"versionNonce": 1326091935,
			"isDeleted": false,
			"id": "vMi0xNBvaN6lk2OafFoaj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": -252.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.1702801775027183,
			"height": 104.14243315621468,
			"seed": 639637197,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "V0hEtnwb"
				}
			],
			"updated": 1712543643747,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "1BWujxaz4DveoGHQCwHx2",
				"gap": 2.235503598899811,
				"focus": 0.006137992831541219
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.1702801775027183,
					104.14243315621468
				]
			]
		},
		{
			"type": "text",
			"version": 24,
			"versionNonce": 240596941,
			"isDeleted": false,
			"id": "V0hEtnwb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -261.5,
			"y": -220.6171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 100,
			"height": 25,
			"seed": 1836714883,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "是虚拟节点",
			"rawText": "是虚拟节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vMi0xNBvaN6lk2OafFoaj",
			"originalText": "是虚拟节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 257,
			"versionNonce": 263370627,
			"isDeleted": false,
			"id": "R1vaQoplM8m7zevhA0O8T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 95,
			"y": -110.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 304,
			"height": 88,
			"seed": 1289972525,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "lhIJq99b"
				},
				{
					"id": "8SfHTRWvm8R8CP-NOglN0",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 60339757,
			"isDeleted": false,
			"id": "lhIJq99b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 137,
			"y": -78.6171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 220,
			"height": 25,
			"seed": 1969435917,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "删除旧节点，插入新节点",
			"rawText": "删除旧节点，插入新节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "R1vaQoplM8m7zevhA0O8T",
			"originalText": "删除旧节点，插入新节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 340,
			"versionNonce": 672583459,
			"isDeleted": false,
			"id": "89OMNwPU5-UozrNnotjqg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -356,
			"y": 95.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 280,
			"height": 126,
			"seed": 1256778093,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PE8cBTxy"
				},
				{
					"id": "NBukSpMiOmA_sID63G-XJ",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 618358925,
			"isDeleted": false,
			"id": "PE8cBTxy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -341.5199508666992,
			"y": 146.3828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 251.03990173339844,
			"height": 25,
			"seed": 445196397,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "调用patchVNode精细化比较",
			"rawText": "调用patchVNode精细化比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "89OMNwPU5-UozrNnotjqg",
			"originalText": "调用patchVNode精细化比较",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 93,
			"versionNonce": 1648688895,
			"isDeleted": false,
			"id": "8SfHTRWvm8R8CP-NOglN0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -31,
			"y": -69.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124,
			"height": 1,
			"seed": 1331290765,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "2sLhlbZP"
				}
			],
			"updated": 1712543643748,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "R1vaQoplM8m7zevhA0O8T",
				"gap": 2,
				"focus": 0.01676176890156919
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					124,
					1
				]
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 1138282221,
			"isDeleted": false,
			"id": "2sLhlbZP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 21,
			"y": -81.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 25,
			"seed": 697452195,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "否",
			"rawText": "否",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "8SfHTRWvm8R8CP-NOglN0",
			"originalText": "否",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 177,
			"versionNonce": 1684719391,
			"isDeleted": false,
			"id": "NBukSpMiOmA_sID63G-XJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": -5.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.548933514777417,
			"height": 99,
			"seed": 2080920547,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Y9T2iNrY"
				}
			],
			"updated": 1712543643750,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "89OMNwPU5-UozrNnotjqg",
				"gap": 2,
				"focus": 0.02435772068628322
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.548933514777417,
					99
				]
			]
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 1058695501,
			"isDeleted": false,
			"id": "Y9T2iNrY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -220.77446675738872,
			"y": 31.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 25,
			"seed": 1782680589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "是",
			"rawText": "是",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "NBukSpMiOmA_sID63G-XJ",
			"originalText": "是",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 362,
			"versionNonce": 1174450911,
			"isDeleted": false,
			"id": "-1Ot4XSRZWw53PDqCwbNY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 257.34200904346835,
			"y": -276.1171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 459.2494159382069,
			"height": 131.5731698695755,
			"seed": 1132944067,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643747,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Sxac85I_JoS6IaRnMtP4-",
				"gap": 3,
				"focus": -0.455802034530065
			},
			"endBinding": {
				"elementId": "1BWujxaz4DveoGHQCwHx2",
				"gap": 2.41765336292562,
				"focus": -0.9491598770406184
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-459.2494159382069,
					131.5731698695755
				]
			]
		},
		{
			"type": "diamond",
			"version": 975,
			"versionNonce": 1744418733,
			"isDeleted": false,
			"id": "sNTrm6gDFDY1yOkTA6wPw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -411.5,
			"y": 321.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387,
			"height": 170,
			"seed": 1231557219,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "M5i1DTDP"
				},
				{
					"id": "rMoF0I_gaz2AiD5rVp9FS",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 512,
			"versionNonce": 2002822563,
			"isDeleted": false,
			"id": "M5i1DTDP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -308.98992919921875,
			"y": 369.3828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.4798583984375,
			"height": 75,
			"seed": 2082328067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "oldVNode和newVNod\ne是否在内存中是同\n一对象",
			"rawText": "oldVNode和newVNode是否在内存中是同一对象",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "sNTrm6gDFDY1yOkTA6wPw",
			"originalText": "oldVNode和newVNode是否在内存中是同一对象",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 42,
			"versionNonce": 182618943,
			"isDeleted": false,
			"id": "rMoF0I_gaz2AiD5rVp9FS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -215,
			"y": 219.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.842170943040401e-14,
			"height": 102.22560062100894,
			"seed": 258933155,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643751,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sNTrm6gDFDY1yOkTA6wPw",
				"gap": 1,
				"focus": 0.015503875968992248
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.842170943040401e-14,
					102.22560062100894
				]
			]
		},
		{
			"type": "rectangle",
			"version": 137,
			"versionNonce": 1545730371,
			"isDeleted": false,
			"id": "qhGG89W75DrNG90klpeon",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136,
			"y": 358.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 268,
			"height": 99,
			"seed": 138530403,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "1UmnWtpI"
				},
				{
					"id": "qj4kNAqkhNFBes59PKSN_",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 1778872429,
			"isDeleted": false,
			"id": "1UmnWtpI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 180,
			"y": 395.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 180,
			"height": 25,
			"seed": 315670147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不做处理，直接返回",
			"rawText": "不做处理，直接返回",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "qhGG89W75DrNG90klpeon",
			"originalText": "不做处理，直接返回",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 79,
			"versionNonce": 1913441119,
			"isDeleted": false,
			"id": "qj4kNAqkhNFBes59PKSN_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39,
			"y": 407.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174,
			"height": 0.5655842663427393,
			"seed": 553704099,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "n3ULmmol"
				}
			],
			"updated": 1712543643752,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "qhGG89W75DrNG90klpeon",
				"gap": 1,
				"focus": -0.010101010101010102
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					174,
					0.5655842663427393
				]
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 972610253,
			"isDeleted": false,
			"id": "n3ULmmol",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 25.5,
			"y": 396.1735529760203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 25,
			"seed": 1601915619,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "是",
			"rawText": "是",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "qj4kNAqkhNFBes59PKSN_",
			"originalText": "是",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 219,
			"versionNonce": 582009987,
			"isDeleted": false,
			"id": "g7ZglWj-1k2NYLBIOrZA-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -426,
			"y": 575.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 412,
			"height": 130,
			"seed": 1546123235,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "b26x0XoP"
				},
				{
					"id": "Uw-cxviQCURtox2ki4-RY",
					"type": "arrow"
				},
				{
					"id": "Y5NauOk7zR_vip34-kE8F",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 822999341,
			"isDeleted": false,
			"id": "b26x0XoP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -316.92993927001953,
			"y": 615.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 193.85987854003906,
			"height": 50,
			"seed": 171259277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "newVNode是否有text\n属性",
			"rawText": "newVNode是否有text属性",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "g7ZglWj-1k2NYLBIOrZA-",
			"originalText": "newVNode是否有text属性",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 112,
			"versionNonce": 1446643583,
			"isDeleted": false,
			"id": "Uw-cxviQCURtox2ki4-RY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": 486.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.1042300506164793,
			"height": 86.36007444623999,
			"seed": 1827042221,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PZKjihkq"
				}
			],
			"updated": 1712543643754,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "g7ZglWj-1k2NYLBIOrZA-",
				"gap": 5.194396259574361,
				"focus": 0.03898496240601504
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.1042300506164793,
					86.36007444623999
				]
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 414206861,
			"isDeleted": false,
			"id": "PZKjihkq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -221.50122426020494,
			"y": 519.0744312808133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 25,
			"seed": 1032576963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "否",
			"rawText": "否",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Uw-cxviQCURtox2ki4-RY",
			"originalText": "否",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 405,
			"versionNonce": 1106624451,
			"isDeleted": false,
			"id": "z2U72gMOoiQ-yV-k3R_eV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 82,
			"y": 561.8828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 367,
			"height": 170,
			"seed": 1705103331,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "2n3odB4B"
				},
				{
					"id": "Y5NauOk7zR_vip34-kE8F",
					"type": "arrow"
				},
				{
					"id": "BPeUtNJM--Hcm_-xjzZy6",
					"type": "arrow"
				},
				{
					"id": "xmrkpTMnYDfkRtdL1N2Sl",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 298,
			"versionNonce": 1360613869,
			"isDeleted": false,
			"id": "2n3odB4B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 178.82006072998047,
			"y": 609.3828125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.85987854003906,
			"height": 75,
			"seed": 893639555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "newVNode的text与\noldVNode中text比\n较",
			"rawText": "newVNode的text与oldVNode中text比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "z2U72gMOoiQ-yV-k3R_eV",
			"originalText": "newVNode的text与oldVNode中text比较",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 127,
			"versionNonce": 1294389247,
			"isDeleted": false,
			"id": "Y5NauOk7zR_vip34-kE8F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -19.170927968303545,
			"y": 646.2522800628142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 106.30747532217414,
			"height": 4.230567996199511,
			"seed": 1869943597,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "EZQIk8J1"
				}
			],
			"updated": 1712543643755,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "g7ZglWj-1k2NYLBIOrZA-",
				"gap": 3.5646238142834576,
				"focus": -0.04034833091436865
			},
			"endBinding": {
				"elementId": "z2U72gMOoiQ-yV-k3R_eV",
				"gap": 1.1076459533246634,
				"focus": -0.12586015538290787
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					106.30747532217414,
					4.230567996199511
				]
			]
		},
		{
			"type": "text",
			"version": 11,
			"versionNonce": 2001898573,
			"isDeleted": false,
			"id": "EZQIk8J1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 24.569008325956517,
			"y": 635.1584297839086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20,
			"height": 25,
			"seed": 1688856589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "是",
			"rawText": "是",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Y5NauOk7zR_vip34-kE8F",
			"originalText": "是",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 116,
			"versionNonce": 1176824579,
			"isDeleted": false,
			"id": "ZEMuv7Fsw8zfleimDQ_R1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 25.455770068152788,
			"y": 824.6534198862596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165,
			"height": 76,
			"seed": 112548035,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9Zcd5rwd"
				},
				{
					"id": "BPeUtNJM--Hcm_-xjzZy6",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 1261796013,
			"isDeleted": false,
			"id": "9Zcd5rwd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 67.95577006815279,
			"y": 850.1534198862596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 80,
			"height": 25,
			"seed": 1294218147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不做处理",
			"rawText": "不做处理",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZEMuv7Fsw8zfleimDQ_R1",
			"originalText": "不做处理",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 218,
			"versionNonce": 1224118947,
			"isDeleted": false,
			"id": "k6fcJipeg_MykDqTmJuPP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 354.20989154540473,
			"y": 823.2666086134657,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 312.73160524958814,
			"height": 196.2653795910839,
			"seed": 10812067,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dsWcXqXc"
				},
				{
					"id": "xmrkpTMnYDfkRtdL1N2Sl",
					"type": "arrow"
				}
			],
			"updated": 1712506770070,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 1433115917,
			"isDeleted": false,
			"id": "dsWcXqXc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 359.9257613088707,
			"y": 858.8992984090077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 301.29986572265625,
			"height": 125,
			"seed": 1878117507,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "将elm中的innerText属性改变为ne\nwVNode中的text属性值\n（oldVNode中有chilrden属性也没\n事，因为innerText属性改变后，\n原来的chilrden也没了）",
			"rawText": "将elm中的innerText属性改变为newVNode中的text属性值\n（oldVNode中有chilrden属性也没事，因为innerText属性改变后，原来的chilrden也没了）",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "k6fcJipeg_MykDqTmJuPP",
			"originalText": "将elm中的innerText属性改变为newVNode中的text属性值\n（oldVNode中有chilrden属性也没事，因为innerText属性改变后，原来的chilrden也没了）",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 74,
			"versionNonce": 136348863,
			"isDeleted": false,
			"id": "BPeUtNJM--Hcm_-xjzZy6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 257.52873200491496,
			"y": 729.2924741105048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 128.7477263795593,
			"height": 90.80729621602222,
			"seed": 1882000685,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "K8PenjuR"
				}
			],
			"updated": 1712543643757,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "z2U72gMOoiQ-yV-k3R_eV",
				"gap": 1,
				"focus": -0.5932980187984281
			},
			"endBinding": {
				"elementId": "ZEMuv7Fsw8zfleimDQ_R1",
				"gap": 4.553649559732548,
				"focus": -0.2896962042964082
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-128.7477263795593,
					90.80729621602222
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 1299084141,
			"isDeleted": false,
			"id": "K8PenjuR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 159.90360709677464,
			"y": 757.6192713948628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 40,
			"height": 25,
			"seed": 2045234285,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "相同",
			"rawText": "相同",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BPeUtNJM--Hcm_-xjzZy6",
			"originalText": "相同",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 124,
			"versionNonce": 1281859839,
			"isDeleted": false,
			"id": "xmrkpTMnYDfkRtdL1N2Sl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 309.6257650566128,
			"y": 714.5315091609754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 143.136734570045,
			"height": 105.56826116555169,
			"seed": 2001872451,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0yol8M2O"
				}
			],
			"updated": 1712543643759,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "z2U72gMOoiQ-yV-k3R_eV",
				"gap": 2.802373273834448,
				"focus": 0.25938423343785777
			},
			"endBinding": {
				"elementId": "k6fcJipeg_MykDqTmJuPP",
				"gap": 3.166838286938628,
				"focus": 0.2748098136478748
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					143.136734570045,
					105.56826116555169
				]
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 1065844173,
			"isDeleted": false,
			"id": "0yol8M2O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 360.8428474850193,
			"y": 754.9128783144043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 40,
			"height": 25,
			"seed": 1384214723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770070,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不同",
			"rawText": "不同",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "xmrkpTMnYDfkRtdL1N2Sl",
			"originalText": "不同",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "diamond",
			"version": 380,
			"versionNonce": 393862161,
			"isDeleted": false,
			"id": "rxpymcl3ceYbV-uoEFbD8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.8616750270125,
			"y": 932.0577530305272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 412,
			"height": 130,
			"seed": 1488474701,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "QWiMU5Jn"
				},
				{
					"id": "os0O53_v93rMQULRUu4J1",
					"type": "arrow"
				},
				{
					"id": "8TN9uGeQ5hfokCqMz_JqQ",
					"type": "arrow"
				},
				{
					"id": "v79gWgmAUPo0I-S2PLEbr",
					"type": "arrow"
				},
				{
					"id": "DmlURBdPeoh3XFSw4kEXZ",
					"type": "arrow"
				}
			],
			"updated": 1712541310418,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 338,
			"versionNonce": 745349581,
			"isDeleted": false,
			"id": "QWiMU5Jn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -308.73163199722734,
			"y": 972.0577530305272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 189.7399139404297,
			"height": 50,
			"seed": 1207074989,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712507222652,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "new和old是否都有chil\nrden属性",
			"rawText": "new和old是否都有chilrden属性",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rxpymcl3ceYbV-uoEFbD8",
			"originalText": "new和old是否都有chilrden属性",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 178,
			"versionNonce": 1978214687,
			"isDeleted": false,
			"id": "os0O53_v93rMQULRUu4J1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -219.2649722088141,
			"y": 702.5780566223435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 5.575383924596679,
			"height": 215.05685667002774,
			"seed": 2092738147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "s1AlTSRL"
				}
			],
			"updated": 1712543643760,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "rxpymcl3ceYbV-uoEFbD8",
				"gap": 14.423866331867323,
				"focus": 0.010830760959485337
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.575383924596679,
					215.05685667002774
				]
			]
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 254946957,
			"isDeleted": false,
			"id": "s1AlTSRL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -320.52228462537784,
			"y": 746.6486834853073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d3d3",
			"width": 209.07992553710938,
			"height": 50,
			"seed": 1986413453,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712506770071,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "没有（意味着newVNode\n有chilrden属性）",
			"rawText": "没有（意味着newVNode有chilrden属性）",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "os0O53_v93rMQULRUu4J1",
			"originalText": "没有（意味着newVNode有chilrden属性）",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 178,
			"versionNonce": 266620063,
			"isDeleted": false,
			"id": "wE-qbR5j4Wrid_PYhlBCH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 51.565548494820064,
			"y": 1177.8665600299782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 317.4437094308405,
			"height": 160,
			"seed": 1318003885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ReynsXh0"
				},
				{
					"id": "v79gWgmAUPo0I-S2PLEbr",
					"type": "arrow"
				}
			],
			"updated": 1712541424751,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 1745838271,
			"isDeleted": false,
			"id": "ReynsXh0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 58.11742030008406,
			"y": 1195.3665600299782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 304.3399658203125,
			"height": 125,
			"seed": 865834179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712541424751,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "只有旧节点有子节点而新节点没有\n，说明更新后的页面，旧节点全部\n都不见了，那么要做的，就是把所\n有的旧节点删除，也就是直接把`D\nOM` 删除",
			"rawText": "只有旧节点有子节点而新节点没有，说明更新后的页面，旧节点全部都不见了，那么要做的，就是把所有的旧节点删除，也就是直接把`DOM` 删除",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wE-qbR5j4Wrid_PYhlBCH",
			"originalText": "只有旧节点有子节点而新节点没有，说明更新后的页面，旧节点全部都不见了，那么要做的，就是把所有的旧节点删除，也就是直接把`DOM` 删除",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 199,
			"versionNonce": 242465681,
			"isDeleted": false,
			"id": "6_XYXHxfLBbKiNZ9XyidI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -327.3309158448448,
			"y": 1179.4190329163293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 292.3016703628709,
			"height": 161.2500000000001,
			"seed": 1773301165,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "8TN9uGeQ5hfokCqMz_JqQ",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "Cj2B3beh"
				}
			],
			"updated": 1712542723575,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 164,
			"versionNonce": 729889073,
			"isDeleted": false,
			"id": "Cj2B3beh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -321.1800806634094,
			"y": 1197.5440329163293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 280,
			"height": 125,
			"seed": 1491827103,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542723575,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "只有新节点有子节点，旧节点没\n有，那么不用比较了，所有节点\n都是全新的，所以直接全部新建\n就好了，新建是指创建出所有新\n`DOM`，并且添加进父节点",
			"rawText": "只有新节点有子节点，旧节点没有，那么不用比较了，所有节点都是全新的，所以直接全部新建就好了，新建是指创建出所有新`DOM`，并且添加进父节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "6_XYXHxfLBbKiNZ9XyidI",
			"originalText": "只有新节点有子节点，旧节点没有，那么不用比较了，所有节点都是全新的，所以直接全部新建就好了，新建是指创建出所有新`DOM`，并且添加进父节点",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 162,
			"versionNonce": 228363409,
			"isDeleted": false,
			"id": "ClR0UJFFkPY_rAJD73F1K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -662.5369897074411,
			"y": 1205.3654537120542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.69260311291657,
			"height": 121.57418659053474,
			"seed": 1851890157,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "1lK8Mnak"
				},
				{
					"id": "DmlURBdPeoh3XFSw4kEXZ",
					"type": "arrow"
				},
				{
					"id": "IX9laDUCODgtb_nIAup7z",
					"type": "arrow"
				}
			],
			"updated": 1712541946690,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 286572913,
			"isDeleted": false,
			"id": "1lK8Mnak",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -656.3006735025454,
			"y": 1241.1525470073216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 221.219970703125,
			"height": 50,
			"seed": 978946673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712541857804,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "进行子节点更新，运行up\ndateChildren函数",
			"rawText": "进行子节点更新，运行updateChildren函数",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ClR0UJFFkPY_rAJD73F1K",
			"originalText": "进行子节点更新，运行updateChildren函数",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 1314922079,
			"isDeleted": false,
			"id": "8TN9uGeQ5hfokCqMz_JqQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -196.4076815633762,
			"y": 1058.8752455851522,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.026699870512601,
			"height": 119.19296303572696,
			"seed": 1457758605,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yD18Jcih"
				}
			],
			"updated": 1712543643764,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rxpymcl3ceYbV-uoEFbD8",
				"gap": 2.2170712107876867,
				"focus": -0.05193158908410427
			},
			"endBinding": {
				"elementId": "6_XYXHxfLBbKiNZ9XyidI",
				"gap": 1.3508242954501384,
				"focus": 0.04361255250802975
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					13.026699870512601,
					119.19296303572696
				]
			]
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 2079134317,
			"isDeleted": false,
			"id": "yD18Jcih",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.89339484106335,
			"y": 1106.8073517687872,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 209.07992553710938,
			"height": 25,
			"seed": 1648499715,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712507304042,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "只有newVNode有子节点",
			"rawText": "只有newVNode有子节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "8TN9uGeQ5hfokCqMz_JqQ",
			"originalText": "只有newVNode有子节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 322,
			"versionNonce": 1483135519,
			"isDeleted": false,
			"id": "v79gWgmAUPo0I-S2PLEbr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -48.44863730768398,
			"y": 1019.3799836714185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 272.9225410637217,
			"height": 153.0832791767583,
			"seed": 490813987,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0dgqDYJf"
				}
			],
			"updated": 1712543643762,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rxpymcl3ceYbV-uoEFbD8",
				"gap": 9.074638592844856,
				"focus": -0.6097870777136929
			},
			"endBinding": {
				"elementId": "wE-qbR5j4Wrid_PYhlBCH",
				"gap": 5.403297181801463,
				"focus": 0.5523388591699465
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					272.9225410637217,
					153.0832791767583
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 128331363,
			"isDeleted": false,
			"id": "0dgqDYJf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -58.699606765686895,
			"y": 1105.4565274733368,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 204.3399200439453,
			"height": 25,
			"seed": 1251606509,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712507317843,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "只有oldVNode有子节点",
			"rawText": "只有oldVNode有子节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "v79gWgmAUPo0I-S2PLEbr",
			"originalText": "只有oldVNode有子节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 402,
			"versionNonce": 495276703,
			"isDeleted": false,
			"id": "DmlURBdPeoh3XFSw4kEXZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -418.3148978057251,
			"y": 1010.1662347555346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 146.45991455941078,
			"height": 187.82839636239532,
			"seed": 562178833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "RvDMsRJ5"
				}
			],
			"updated": 1712543643765,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rxpymcl3ceYbV-uoEFbD8",
				"gap": 12.035497314640246,
				"focus": 0.9428729792761773
			},
			"endBinding": {
				"elementId": "ClR0UJFFkPY_rAJD73F1K",
				"gap": 7.37082259412432,
				"focus": -0.4397723033270303
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-146.45991455941078,
					187.82839636239532
				]
			]
		},
		{
			"type": "text",
			"version": 27,
			"versionNonce": 908778065,
			"isDeleted": false,
			"id": "RvDMsRJ5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -566.8786288091655,
			"y": 1072.9946311179299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140,
			"height": 25,
			"seed": 836768703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712541274874,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "两者都有子节点",
			"rawText": "两者都有子节点",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "DmlURBdPeoh3XFSw4kEXZ",
			"originalText": "两者都有子节点",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 229,
			"versionNonce": 627262449,
			"isDeleted": false,
			"id": "PvSPbkilYhvffscOo9A0R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -663.7536288091655,
			"y": 1406.7446311179299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.9999999999999,
			"height": 112.5,
			"seed": 1791230193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "gGk2R2dE"
				},
				{
					"id": "IX9laDUCODgtb_nIAup7z",
					"type": "arrow"
				},
				{
					"id": "OjwepT85M6GpMwt5E80hr",
					"type": "arrow"
				}
			],
			"updated": 1712542766040,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 176,
			"versionNonce": 1532755217,
			"isDeleted": false,
			"id": "gGk2R2dE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -656.353604395103,
			"y": 1450.4946311179299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 235.199951171875,
			"height": 25,
			"seed": 1378104305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712541954152,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "进行子节点数组的diff算法",
			"rawText": "进行子节点数组的diff算法",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "PvSPbkilYhvffscOo9A0R",
			"originalText": "进行子节点数组的diff算法",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 229,
			"versionNonce": 224627487,
			"isDeleted": false,
			"id": "IX9laDUCODgtb_nIAup7z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -547.5910493094866,
			"y": 1329.2446311179299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2056173568033728,
			"height": 75,
			"seed": 312905343,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643767,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ClR0UJFFkPY_rAJD73F1K",
				"gap": 2.3049908153409433,
				"focus": 0.00752110335507765
			},
			"endBinding": {
				"elementId": "PvSPbkilYhvffscOo9A0R",
				"gap": 2.5,
				"focus": -0.08726823238566134
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.2056173568033728,
					75
				]
			]
		},
		{
			"type": "rectangle",
			"version": 349,
			"versionNonce": 1087892113,
			"isDeleted": false,
			"id": "WjSCz8Ptjg7bhDGTgbDJk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -661.7893430948802,
			"y": 1584.9589168322157,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 267.4999999999999,
			"height": 131.25,
			"seed": 574647441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "7lzz6wnyhkRUnV1sTfBQL",
					"type": "arrow"
				},
				{
					"id": "OjwepT85M6GpMwt5E80hr",
					"type": "arrow"
				},
				{
					"id": "_TIz_YViFW3WGxwdk8jLX",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "3nuobmKi"
				},
				{
					"id": "5OPX_gCwHF7WpplOeY5JF",
					"type": "arrow"
				}
			],
			"updated": 1712544869845,
			"link": null,
			"locked": false
		},
		{
			"id": "3nuobmKi",
			"type": "text",
			"x": -649.7292692423412,
			"y": 1625.5839168322157,
			"width": 243.37985229492188,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1790304223,
			"version": 80,
			"versionNonce": 1805667935,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1712544495041,
			"link": null,
			"locked": false,
			"text": "while(oldStart <= oldEnd\n&& newStart >= newEnd)",
			"rawText": "while(oldStart <= oldEnd && newStart >= newEnd)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "WjSCz8Ptjg7bhDGTgbDJk",
			"originalText": "while(oldStart <= oldEnd && newStart >= newEnd)",
			"lineHeight": 1.25
		},
		{
			"type": "diamond",
			"version": 659,
			"versionNonce": 1294653983,
			"isDeleted": false,
			"id": "FDMCOO1HqKdgzaxEUrPUk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -674.8488669044042,
			"y": 1808.482726356024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 299.9999999999999,
			"height": 120,
			"seed": 1811980593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "qDZAtQDB"
				},
				{
					"id": "SmkKLLt3M4NG336CSEnZ9",
					"type": "arrow"
				},
				{
					"id": "7lzz6wnyhkRUnV1sTfBQL",
					"type": "arrow"
				},
				{
					"id": "FmCAjdVtYuYZ2L_qBTrDj",
					"type": "arrow"
				},
				{
					"id": "_TIz_YViFW3WGxwdk8jLX",
					"type": "arrow"
				}
			],
			"updated": 1712544742520,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 457,
			"versionNonce": 673726015,
			"isDeleted": false,
			"id": "qDZAtQDB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -584.8488669044042,
			"y": 1843.482726356024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120,
			"height": 50,
			"seed": 71497425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712544742520,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "新头与旧头节\n点比较",
			"rawText": "新头与旧头节点比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "FDMCOO1HqKdgzaxEUrPUk",
			"originalText": "新头与旧头节点比较",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "diamond",
			"version": 577,
			"versionNonce": 1645542193,
			"isDeleted": false,
			"id": "C0EBc34LxvkbJa1hCLbtT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -680.1822002377372,
			"y": 1989.2446311179292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.2857142857142,
			"height": 120,
			"seed": 611377919,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "oSK0pYdM"
				},
				{
					"id": "SmkKLLt3M4NG336CSEnZ9",
					"type": "arrow"
				},
				{
					"id": "x9fNcZagrjR_ZEZSc1zV8",
					"type": "arrow"
				},
				{
					"id": "BOJH-s9uZShdzSfdfZ1Rs",
					"type": "arrow"
				}
			],
			"updated": 1712542841099,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 356,
			"versionNonce": 829593745,
			"isDeleted": false,
			"id": "oSK0pYdM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -593.1107716663087,
			"y": 2024.2446311179292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140,
			"height": 50,
			"seed": 2105213119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542723586,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "新尾与旧尾节点\n比较",
			"rawText": "新尾与旧尾节点比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "C0EBc34LxvkbJa1hCLbtT",
			"originalText": "新尾与旧尾节点比较",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "diamond",
			"version": 467,
			"versionNonce": 1737361361,
			"isDeleted": false,
			"id": "trQARy7sxEJeZOj1EFd24",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -670.1822002377371,
			"y": 2190.6732025465003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 305.71428571428555,
			"height": 120,
			"seed": 461201823,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DacHb4Gi"
				},
				{
					"id": "x9fNcZagrjR_ZEZSc1zV8",
					"type": "arrow"
				},
				{
					"id": "TRIosG1lBOjYACDfuJ0QX",
					"type": "arrow"
				},
				{
					"id": "gMVuBFCLir7hCFSYc0eo_",
					"type": "arrow"
				}
			],
			"updated": 1712542835673,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 385,
			"versionNonce": 1552686577,
			"isDeleted": false,
			"id": "DacHb4Gi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -587.2536288091658,
			"y": 2225.6732025465003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140,
			"height": 50,
			"seed": 258455505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542723588,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "新尾与旧头节点\n比较",
			"rawText": "新尾与旧头节点比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "trQARy7sxEJeZOj1EFd24",
			"originalText": "新尾与旧头节点比较",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "diamond",
			"version": 699,
			"versionNonce": 470978417,
			"isDeleted": false,
			"id": "YVEV-OHomVK3m1HBFPy2U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -665.8964859520229,
			"y": 2414.958916832216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 315.71428571428567,
			"height": 120,
			"seed": 1844072401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "fXI9wyfA"
				},
				{
					"id": "TRIosG1lBOjYACDfuJ0QX",
					"type": "arrow"
				},
				{
					"id": "HHND74QY0rE-eqjuWX9Sf",
					"type": "arrow"
				}
			],
			"updated": 1712542725615,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 435,
			"versionNonce": 397491679,
			"isDeleted": false,
			"id": "fXI9wyfA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.9679145234514,
			"y": 2449.958916832216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140,
			"height": 50,
			"seed": 1894608273,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542490347,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "新头与旧尾节点\n比较",
			"rawText": "新头与旧尾节点 比较",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "YVEV-OHomVK3m1HBFPy2U",
			"originalText": "新头与旧尾节点 比较",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 598,
			"versionNonce": 233765503,
			"isDeleted": false,
			"id": "SmkKLLt3M4NG336CSEnZ9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -522.7821511980496,
			"y": 1930.4734595326304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.8627466087179982,
			"height": 51.15226443328129,
			"seed": 1304364703,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ddaz5dtM"
				}
			],
			"updated": 1712544742520,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FDMCOO1HqKdgzaxEUrPUk",
				"gap": 2.6159082962658076,
				"focus": -0.021587301587303317
			},
			"endBinding": {
				"elementId": "C0EBc34LxvkbJa1hCLbtT",
				"gap": 7.6429341682466685,
				"focus": -0.01111111111110982
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.8627466087179982,
					51.15226443328129
				]
			]
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 51266897,
			"isDeleted": false,
			"id": "ddaz5dtM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -555.8205937666994,
			"y": 1911.214786038337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60,
			"height": 25,
			"seed": 1147300287,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542421729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不相似",
			"rawText": "不相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SmkKLLt3M4NG336CSEnZ9",
			"originalText": "不相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 358,
			"versionNonce": 1489426879,
			"isDeleted": false,
			"id": "x9fNcZagrjR_ZEZSc1zV8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -519.5564917060253,
			"y": 2111.670074212907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.7396746275397845,
			"height": 71.74033603602311,
			"seed": 1555707121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xEHlCyJm"
				}
			],
			"updated": 1712543643774,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "C0EBc34LxvkbJa1hCLbtT",
				"gap": 3.5082320772282216,
				"focus": -0.006993006993009034
			},
			"endBinding": {
				"elementId": "trQARy7sxEJeZOj1EFd24",
				"gap": 7.280553561531505,
				"focus": 0.020129403306973884
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					2.7396746275397845,
					71.74033603602311
				]
			]
		},
		{
			"type": "text",
			"version": 10,
			"versionNonce": 1185652849,
			"isDeleted": false,
			"id": "xEHlCyJm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -548.3484614666976,
			"y": 2135.078295114426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60,
			"height": 25,
			"seed": 1685366207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542480447,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不相似",
			"rawText": "不相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "x9fNcZagrjR_ZEZSc1zV8",
			"originalText": "不相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 694,
			"versionNonce": 404635263,
			"isDeleted": false,
			"id": "TRIosG1lBOjYACDfuJ0QX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -508.02363447716493,
			"y": 2317.287689634888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.3710127592643744,
			"height": 91.39063873733039,
			"seed": 1199985503,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZKgQhXHu"
				}
			],
			"updated": 1712543643776,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "trQARy7sxEJeZOj1EFd24",
				"gap": 9.55572654951061,
				"focus": -0.06738809640924819
			},
			"endBinding": {
				"elementId": "YVEV-OHomVK3m1HBFPy2U",
				"gap": 6.425156863451143,
				"focus": -0.014884496308644413
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.3710127592643744,
					91.39063873733039
				]
			]
		},
		{
			"type": "text",
			"version": 10,
			"versionNonce": 1980684479,
			"isDeleted": false,
			"id": "ZKgQhXHu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -541.4027649414338,
			"y": 2337.23119741738,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60,
			"height": 25,
			"seed": 982829585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542484879,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不相似",
			"rawText": "不相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "TRIosG1lBOjYACDfuJ0QX",
			"originalText": "不相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 637,
			"versionNonce": 1642309311,
			"isDeleted": false,
			"id": "7lzz6wnyhkRUnV1sTfBQL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.1900801795458,
			"y": 1720.6732025465008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.98675147804056,
			"height": 87.38877258283128,
			"seed": 276402193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9StmYUsd"
				}
			],
			"updated": 1712544742520,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "WjSCz8Ptjg7bhDGTgbDJk",
				"gap": 4.464285714285097,
				"focus": 0.04028147151573534
			},
			"endBinding": {
				"elementId": "FDMCOO1HqKdgzaxEUrPUk",
				"gap": 1.74457660549416,
				"focus": 0.05650793650793738
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.98675147804056,
					87.38877258283128
				]
			]
		},
		{
			"id": "9StmYUsd",
			"type": "text",
			"x": -607.3492098487723,
			"y": 1746.8145015406985,
			"width": 160,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1306877119,
			"version": 85,
			"versionNonce": 1307474449,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1712544732107,
			"link": null,
			"locked": false,
			"text": "条件成立进入循环",
			"rawText": "条件成立进入循环",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "7lzz6wnyhkRUnV1sTfBQL",
			"originalText": "条件成立进入循环",
			"lineHeight": 1.25
		},
		{
			"type": "diamond",
			"version": 910,
			"versionNonce": 390616831,
			"isDeleted": false,
			"id": "fNM1cQ8rwmNQ44XjtfOcO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -665.896485952023,
			"y": 2647.816059689359,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 327.1428571428571,
			"height": 220,
			"seed": 685757887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ksfRA2eu"
				},
				{
					"id": "HHND74QY0rE-eqjuWX9Sf",
					"type": "arrow"
				},
				{
					"id": "B9V617ix_SE3lNmplPX8E",
					"type": "arrow"
				},
				{
					"id": "vqMlaLgmoW2hqTSmMBQyU",
					"type": "arrow"
				}
			],
			"updated": 1712543464284,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 705,
			"versionNonce": 1925460223,
			"isDeleted": false,
			"id": "ksfRA2eu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.1407551868165,
			"y": 2707.816059689359,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.05996704101562,
			"height": 100,
			"seed": 2125972415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543463036,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "newStartVnode\n节点有key且在旧\n子节点数组中找\n到sameVnode",
			"rawText": "newStartVnode\n节点有key且在旧子节点数组中找到sameVnode",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "fNM1cQ8rwmNQ44XjtfOcO",
			"originalText": "newStartVnode\n节点有key且在旧子节点数组中找到sameVnode",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 1191,
			"versionNonce": 733447935,
			"isDeleted": false,
			"id": "HHND74QY0rE-eqjuWX9Sf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -496.5721812747124,
			"y": 2531.6701560677247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.20523937720759,
			"height": 111.73754708863544,
			"seed": 628439359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "hA9OqVxr"
				}
			],
			"updated": 1712543643777,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "YVEV-OHomVK3m1HBFPy2U",
				"gap": 1,
				"focus": -0.09904119333913508
			},
			"endBinding": {
				"elementId": "fNM1cQ8rwmNQ44XjtfOcO",
				"gap": 5.044570639467963,
				"focus": -0.06635467255895704
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-8.20523937720759,
					111.73754708863544
				]
			]
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 889071089,
			"isDeleted": false,
			"id": "hA9OqVxr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -340.1822002377371,
			"y": 2606.306144733478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60,
			"height": 25,
			"seed": 1108982111,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542723188,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不相似",
			"rawText": "不相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "HHND74QY0rE-eqjuWX9Sf",
			"originalText": "不相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 297,
			"versionNonce": 591570655,
			"isDeleted": false,
			"id": "OjwepT85M6GpMwt5E80hr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -537.8192201599907,
			"y": 1523.5303454036434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.6645999476493216,
			"height": 60.00000000000023,
			"seed": 1850074207,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712544495042,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PvSPbkilYhvffscOo9A0R",
				"gap": 4.285714285713539,
				"focus": -0.0013071895424838578
			},
			"endBinding": {
				"elementId": "WjSCz8Ptjg7bhDGTgbDJk",
				"gap": 1.4285714285722406,
				"focus": -0.04613821138211541
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.6645999476493216,
					60.00000000000023
				]
			]
		},
		{
			"type": "rectangle",
			"version": 314,
			"versionNonce": 169410015,
			"isDeleted": false,
			"id": "q7f8HjdgiIJn2GfxXBJ43",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -216.37267642821325,
			"y": 1832.1017739750723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 232.8571428571429,
			"height": 118.33333333333326,
			"seed": 146509439,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "FmCAjdVtYuYZ2L_qBTrDj",
					"type": "arrow"
				},
				{
					"id": "_TIz_YViFW3WGxwdk8jLX",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "mscBUIGC"
				},
				{
					"id": "EIEFWV9C2kYVjYiG3UU_4",
					"type": "arrow"
				}
			],
			"updated": 1712543191857,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 857467391,
			"isDeleted": false,
			"id": "mscBUIGC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -206.99406990442696,
			"y": 1853.7684406417388,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 214.0999298095703,
			"height": 75,
			"seed": 388711473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543191857,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "直接 `patchVnode` ，\n同时新老 `VNode` 节点\n的开始索引都加 1",
			"rawText": "直接 `patchVnode` ，同时新老 `VNode` 节点的开始索引都加 1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "q7f8HjdgiIJn2GfxXBJ43",
			"originalText": "直接 `patchVnode` ，同时新老 `VNode` 节点的开始索引都加 1",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 230,
			"versionNonce": 1472626065,
			"isDeleted": false,
			"id": "OofZ_C5qGtDm2-e7WKTUx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -220.18220023773722,
			"y": 2012.1017739750723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 227.142857142857,
			"height": 135,
			"seed": 609136465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "BOJH-s9uZShdzSfdfZ1Rs",
					"type": "arrow"
				},
				{
					"id": "EIEFWV9C2kYVjYiG3UU_4",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "a7O2LOdB"
				}
			],
			"updated": 1712543141410,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 788412721,
			"isDeleted": false,
			"id": "a7O2LOdB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -214.10071612431653,
			"y": 2042.1017739750723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 214.97988891601562,
			"height": 75,
			"seed": 26765727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543176516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "同样直接 `patchVnode`\n，同时新老 `VNode`\n节点的结束索引都减 1",
			"rawText": "同样直接 `patchVnode` ，同时新老 `VNode` 节点的结束索引都减 1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "OofZ_C5qGtDm2-e7WKTUx",
			"originalText": "同样直接 `patchVnode` ，同时新老 `VNode` 节点的结束索引都减 1",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 257,
			"versionNonce": 458015153,
			"isDeleted": false,
			"id": "4-P1lNOg-S5KJ2Po72AD4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -225.6583907139277,
			"y": 2210.9112977845953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 231.42857142857133,
			"height": 185,
			"seed": 1449293169,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "gMVuBFCLir7hCFSYc0eo_",
					"type": "arrow"
				},
				{
					"id": "_RjYk6XZ1at_BJTUC5arR",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "5UBQtEGh"
				}
			],
			"updated": 1712543226325,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 2089509777,
			"isDeleted": false,
			"id": "5UBQtEGh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -220.55407509241547,
			"y": 2215.9112977845953,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 221.21994018554688,
			"height": 175,
			"seed": 1323326993,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543226325,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "在 `patchVnode` 后，\n还需要将当前真实 `dom\n` 节点移动到 `oldEndVn\node` 的后面，同时老 `V\nNode` 节点开始索引加\n1，新 `VNode` 节点的结\n束索引减 1",
			"rawText": "在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldEndVnode` 的后面，同时老 `VNode` 节点开始索引加 1，新 `VNode` 节点的结束索引减 1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "4-P1lNOg-S5KJ2Po72AD4",
			"originalText": "在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldEndVnode` 的后面，同时老 `VNode` 节点开始索引加 1，新 `VNode` 节点的结束索引减 1",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "rectangle",
			"version": 292,
			"versionNonce": 1153507089,
			"isDeleted": false,
			"id": "PbciKNianef_NYhZcvsj3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.99172404726107,
			"y": 2474.958916832215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 232.85714285714278,
			"height": 210,
			"seed": 271539633,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "LwdXE6hxYylIszuePybvq",
					"type": "arrow"
				},
				{
					"id": "CIJSUXRmneGWwaaGcPNDN",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "ighKJXn7"
				}
			],
			"updated": 1712543223635,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 31,
			"versionNonce": 642585841,
			"isDeleted": false,
			"id": "ighKJXn7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -218.86312515286937,
			"y": 2479.958916832215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 222.59994506835938,
			"height": 200,
			"seed": 278365119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543223635,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "在 `patchVnode` 后，\n还需要将当前真实 `dom`\n节点移动到 `oldStart\nVnode` 的前面，同时老\n`VNode` 节点结束索引\n减\n1，新 `VNode` 节点的开\n始索引加 1",
			"rawText": "在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldStartVnode` 的前面，同时老 `VNode` 节点结束索引减 1，新 `VNode` 节点的开始索引加 1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "PbciKNianef_NYhZcvsj3",
			"originalText": "在 `patchVnode` 后，还需要将当前真实 `dom` 节点移动到 `oldStartVnode` 的前面，同时老 `VNode` 节点结束索引减 1，新 `VNode` 节点的开始索引加 1",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 607,
			"versionNonce": 88752895,
			"isDeleted": false,
			"id": "FmCAjdVtYuYZ2L_qBTrDj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -397.4876056684865,
			"y": 1881.8239361473716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 175.40064352598756,
			"height": 12.174562291872917,
			"seed": 1865670335,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "0znJ6tL6"
				}
			],
			"updated": 1712544742520,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FDMCOO1HqKdgzaxEUrPUk",
				"gap": 3.9791858180802393,
				"focus": 0.07142857142857793
			},
			"endBinding": {
				"elementId": "q7f8HjdgiIJn2GfxXBJ43",
				"gap": 5.714285714285666,
				"focus": -0.16666666666667154
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					175.40064352598756,
					12.174562291872917
				]
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 1920596753,
			"isDeleted": false,
			"id": "0znJ6tL6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -331.61077166630855,
			"y": 1849.6017739750719,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40,
			"height": 25,
			"seed": 1443720511,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542821040,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "相似",
			"rawText": "相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "FmCAjdVtYuYZ2L_qBTrDj",
			"originalText": "相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 334,
			"versionNonce": 1470932031,
			"isDeleted": false,
			"id": "BOJH-s9uZShdzSfdfZ1Rs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -392.6360168747127,
			"y": 2063.2557519333204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.2663901474588,
			"height": 10.999112894369318,
			"seed": 355045073,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "SWiYhJS1"
				}
			],
			"updated": 1712543643781,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "C0EBc34LxvkbJa1hCLbtT",
				"gap": 3.5514141323270465,
				"focus": 0.09042594903402412
			},
			"endBinding": {
				"elementId": "OofZ_C5qGtDm2-e7WKTUx",
				"gap": 6.1874264895166675,
				"focus": -0.034334844024265204
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					166.2663901474588,
					10.999112894369318
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 856153855,
			"isDeleted": false,
			"id": "SWiYhJS1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -314.2453468232293,
			"y": 2051.030345403644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40,
			"height": 25,
			"seed": 2006027441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542827626,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "相似",
			"rawText": "相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BOJH-s9uZShdzSfdfZ1Rs",
			"originalText": "相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 425,
			"versionNonce": 287275167,
			"isDeleted": false,
			"id": "gMVuBFCLir7hCFSYc0eo_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -396.00418720431713,
			"y": 2264.251999224497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.01551285801565,
			"height": 30.919162811194838,
			"seed": 376042833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "IMKoB1sX"
				}
			],
			"updated": 1712543643783,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "trQARy7sxEJeZOj1EFd24",
				"gap": 1.1170964214611772,
				"focus": -0.1722475431576372
			},
			"endBinding": {
				"elementId": "4-P1lNOg-S5KJ2Po72AD4",
				"gap": 13.330283632373778,
				"focus": -0.14894277151835575
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					157.01551285801565,
					30.919162811194838
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 1082441855,
			"isDeleted": false,
			"id": "IMKoB1sX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -322.81677539465784,
			"y": 2249.6017739750714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40,
			"height": 25,
			"seed": 1895899953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542828741,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "相似",
			"rawText": "相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gMVuBFCLir7hCFSYc0eo_",
			"originalText": "相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 354,
			"versionNonce": 1130568927,
			"isDeleted": false,
			"id": "LwdXE6hxYylIszuePybvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -356.40678120491907,
			"y": 2476.3058879243345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.3704878109985,
			"height": 57.086380059750354,
			"seed": 675420721,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "lJo7BBXU"
				}
			],
			"updated": 1712543643784,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "PbciKNianef_NYhZcvsj3",
				"gap": 9.044569346659443,
				"focus": -0.07233822601602899
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					123.3704878109985,
					57.086380059750354
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 1887048095,
			"isDeleted": false,
			"id": "lJo7BBXU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -294.2453468232293,
			"y": 2471.030345403644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40,
			"height": 25,
			"seed": 1648471057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542829845,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "相似",
			"rawText": "相似",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LwdXE6hxYylIszuePybvq",
			"originalText": "相似",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1649,
			"versionNonce": 2116520735,
			"isDeleted": false,
			"id": "_TIz_YViFW3WGxwdk8jLX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 13.888203031970335,
			"y": 1827.5036014719944,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 536.9724182168344,
			"height": 73.97325606835102,
			"seed": 674477823,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "56zKTE3V"
				}
			],
			"updated": 1712544742521,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "q7f8HjdgiIJn2GfxXBJ43",
				"focus": 0.9991686343947582,
				"gap": 4.5981725030777625
			},
			"endBinding": {
				"elementId": "FDMCOO1HqKdgzaxEUrPUk",
				"gap": 16.734860488081598,
				"focus": -1.275093098569449
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-39.78468898399311,
					-73.97325606835102
				],
				[
					-536.9724182168344,
					-35.6624363367298
				]
			]
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 1290722367,
			"isDeleted": false,
			"id": "56zKTE3V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -95.89648595202277,
			"y": 1741.0303454036434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140,
			"height": 25,
			"seed": 1015674609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712542969500,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "进入下一次循环",
			"rawText": "进入下一次循环",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_TIz_YViFW3WGxwdk8jLX",
			"originalText": "进入下一次循环",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 427,
			"versionNonce": 808174687,
			"isDeleted": false,
			"id": "EIEFWV9C2kYVjYiG3UU_4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 8.38922833369135,
			"y": 2088.3478779002676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.99999999999999,
			"height": 267.618726810907,
			"seed": 814686431,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643781,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "OofZ_C5qGtDm2-e7WKTUx",
				"gap": 1.4285714285715585,
				"focus": 0.8199459014465503
			},
			"endBinding": {
				"elementId": "q7f8HjdgiIJn2GfxXBJ43",
				"gap": 20,
				"focus": -1.192213344547239
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					69.99999999999999,
					-149.1032467823386
				],
				[
					30.4743632103811,
					-267.618726810907
				]
			]
		},
		{
			"type": "arrow",
			"version": 253,
			"versionNonce": 1896156351,
			"isDeleted": false,
			"id": "_RjYk6XZ1at_BJTUC5arR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 15.770180714643743,
			"y": 2319.089919368143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.61904761904759,
			"height": 378.4167168216427,
			"seed": 1363980945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643783,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "4-P1lNOg-S5KJ2Po72AD4",
				"gap": 10.000000000000114,
				"focus": 0.9037998534491803
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					62.61904761904759,
					-201.27385967878536
				],
				[
					61.19047619047626,
					-378.4167168216427
				]
			]
		},
		{
			"type": "arrow",
			"version": 240,
			"versionNonce": 466233599,
			"isDeleted": false,
			"id": "CIJSUXRmneGWwaaGcPNDN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 23.15113309559615,
			"y": 2605.7445825467557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 68.09523809523807,
			"height": 515.071380000255,
			"seed": 1529539473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712543643785,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PbciKNianef_NYhZcvsj3",
				"gap": 14.285714285714448,
				"focus": 0.9796251018744921
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					68.09523809523807,
					-315.07138000025543
				],
				[
					63.80952380952385,
					-515.071380000255
				]
			]
		},
		{
			"type": "rectangle",
			"version": 217,
			"versionNonce": 105596031,
			"isDeleted": false,
			"id": "73rUtZvdD5fX-4EF5p4AH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -855.9001136261336,
			"y": 2938.6206414518215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 235,
			"height": 126.66666666666652,
			"seed": 1893319377,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "B9V617ix_SE3lNmplPX8E",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "qIfezPdv"
				}
			],
			"updated": 1712544851953,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 176970911,
			"isDeleted": false,
			"id": "qIfezPdv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -850.8900580841414,
			"y": 2951.9539747851545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.97988891601562,
			"height": 100,
			"seed": 1673925425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712544851953,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "进行`patchVnode`，同时\n将这个真实 `dom`移动到\n`oldStartVnode` 对应\n的真实 `dom` 的前面",
			"rawText": "进行`patchVnode`，同时将这个真实 `dom`移动到 `oldStartVnode` 对应的真实 `dom` 的前面",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "73rUtZvdD5fX-4EF5p4AH",
			"originalText": "进行`patchVnode`，同时将这个真实 `dom`移动到 `oldStartVnode` 对应的真实 `dom` 的前面",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "rectangle",
			"version": 266,
			"versionNonce": 828324831,
			"isDeleted": false,
			"id": "d46TRVgNniquffjGt1hT2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -333.5667802928,
			"y": 2930.6206414518206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 246.66666666666674,
			"height": 135,
			"seed": 1298344113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "vqMlaLgmoW2hqTSmMBQyU",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "LLpAXavq"
				}
			],
			"updated": 1712544850898,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 1391093759,
			"isDeleted": false,
			"id": "LLpAXavq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -327.25339782616584,
			"y": 2935.6206414518206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 234.03990173339844,
			"height": 125,
			"seed": 1666664209,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712544850898,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "调用 `createElm` 创建一\n个新的 `dom` 节点放到`o\nldStartVnode` 对应的真\n实 `dom` 的前面\n",
			"rawText": "调用 `createElm` 创建一个新的 `dom` 节点放到`oldStartVnode` 对应的真实 `dom` 的前面\n",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "d46TRVgNniquffjGt1hT2",
			"originalText": "调用 `createElm` 创建一个新的 `dom` 节点放到`oldStartVnode` 对应的真实 `dom` 的前面\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 415,
			"versionNonce": 1776746719,
			"isDeleted": false,
			"id": "B9V617ix_SE3lNmplPX8E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -639.5276236850159,
			"y": 2778.5343024692324,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.95459827548711,
			"height": 158.41967231592298,
			"seed": 1850810847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9qkzUrXA"
				}
			],
			"updated": 1712544851953,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fNM1cQ8rwmNQ44XjtfOcO",
				"gap": 2.477384366223646,
				"focus": 0.7445281481889449
			},
			"endBinding": {
				"elementId": "73rUtZvdD5fX-4EF5p4AH",
				"gap": 1.6666666666662877,
				"focus": -0.4173706224883114
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-118.95459827548711,
					158.41967231592298
				]
			]
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 852319615,
			"isDeleted": false,
			"id": "9qkzUrXA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -692.0667802928001,
			"y": 2801.953974785154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 80,
			"height": 25,
			"seed": 1658256049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543403409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "条件成立",
			"rawText": "条件成立",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "B9V617ix_SE3lNmplPX8E",
			"originalText": "条件成立",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 432,
			"versionNonce": 1040299071,
			"isDeleted": false,
			"id": "vqMlaLgmoW2hqTSmMBQyU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.57164830074817,
			"y": 2791.003185632659,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140.81169583431392,
			"height": 131.28412248582845,
			"seed": 1287190033,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xuowh7f9"
				}
			],
			"updated": 1712544850898,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fNM1cQ8rwmNQ44XjtfOcO",
				"gap": 9.22534202196104,
				"focus": -0.5802059722858769
			},
			"endBinding": {
				"elementId": "d46TRVgNniquffjGt1hT2",
				"gap": 8.33333333333303,
				"focus": 0.3106810909644961
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					140.81169583431392,
					131.28412248582845
				]
			]
		},
		{
			"type": "text",
			"version": 10,
			"versionNonce": 1368753745,
			"isDeleted": false,
			"id": "xuowh7f9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -369.56678029280016,
			"y": 2804.453974785154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60,
			"height": 25,
			"seed": 1075034591,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712543411352,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "不成立",
			"rawText": "不成立",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vqMlaLgmoW2hqTSmMBQyU",
			"originalText": "不成立",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "UQfKp4U06dh2jvMWnImEv",
			"type": "rectangle",
			"x": -212.50567777742003,
			"y": 1511.8878680509213,
			"width": 281.33333333333314,
			"height": 110.66666666666654,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1007751249,
			"version": 234,
			"versionNonce": 1375369713,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "5OPX_gCwHF7WpplOeY5JF",
					"type": "arrow"
				}
			],
			"updated": 1712544894036,
			"link": null,
			"locked": false
		},
		{
			"id": "5OPX_gCwHF7WpplOeY5JF",
			"type": "arrow",
			"x": -383.17234444408666,
			"y": 1629.4533506512237,
			"width": 165.33333333333326,
			"height": 54.59049798301953,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 739598719,
			"version": 345,
			"versionNonce": 604082993,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "5RgQXZCq"
				}
			],
			"updated": 1712544886769,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					165.33333333333326,
					-54.59049798301953
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "WjSCz8Ptjg7bhDGTgbDJk",
				"gap": 11.116998650793619,
				"focus": 0.24135035980600936
			},
			"endBinding": {
				"elementId": "UQfKp4U06dh2jvMWnImEv",
				"gap": 5.333333333333371,
				"focus": 0.39856127807935043
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "5RgQXZCq",
			"type": "text",
			"x": -330.50567777742003,
			"y": 1613.3878680509215,
			"width": 100,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 837913471,
			"version": 19,
			"versionNonce": 1639565201,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1712544875471,
			"link": null,
			"locked": false,
			"text": "条件不成立",
			"rawText": "条件不成立",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "5OPX_gCwHF7WpplOeY5JF",
			"originalText": "条件不成立",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 1268650289,
			"isDeleted": true,
			"id": "Q9hXMfC7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.4679145234516,
			"y": 1642.3696311179299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10,
			"height": 25,
			"seed": 233752081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712544428933,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "",
			"rawText": "",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "WjSCz8Ptjg7bhDGTgbDJk",
			"originalText": "",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "XqoFgQAJ",
			"type": "text",
			"x": -561.1462230981103,
			"y": 1628.9832497933694,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1586678431,
			"version": 4,
			"versionNonce": 741800863,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1712544446166,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "fZevOMa8",
			"type": "text",
			"x": -76.83901111075346,
			"y": 1554.7212013842545,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 133211455,
			"version": 2,
			"versionNonce": 1029182417,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1712544894037,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "UQfKp4U06dh2jvMWnImEv",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "JVsQcJBj",
			"type": "text",
			"x": -44.50567777742003,
			"y": 1551.8878680509215,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 450491057,
			"version": 2,
			"versionNonce": 1378982143,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1712544893493,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 908.2140111107533,
		"scrollY": -1145.5337013842548,
		"zoom": {
			"value": 0.7500000000000001
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%