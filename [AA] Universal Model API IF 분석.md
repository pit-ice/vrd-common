
IPF 에서 제공하는 물성 예측 모델에 대한  API. 

물성은 총 5개(MI, I23, I30, TS, FM)의 결과를 반환한다.



#### 물성예측을 위한 Input Source 항목
```
            "PP H730F": NaN,
            "PP B330F": NaN,
            "PP BX3500": NaN,
            "PP BX3800": 10.0,
            "PP BX3900": 46.0,
            "PP BX3910": NaN,
            "PP BX3920": NaN,
            "PP BX3950": NaN,
            "PP HX3700": NaN,
            "PP HX3800": NaN,
            "PP HX3900": NaN,
            "PP BH3820": NaN,
            "POE Solumer 851": 5.0,
            "POE Solumer 8605": NaN,
            "POE Solumer 861": NaN,
            "POE Solumer 865": NaN,
            "POE Solumer 8613": NaN,
            "POE Solumer 8705": 5.0,
            "POE Solumer 871": NaN,
            "POE Solumer 875": 12.0,
            "POE Solumer 8730": NaN,
            "POE Solumer 883": NaN,
            "POE Solumer 891": NaN,
            "Filler Wollastonite M-1250": NaN,
            "Filler Whisker WS-1CY": NaN,
            "Filler TALC KCM6300": NaN,
            "Filler TALC 3000c": 22.0,
            "Filler TALC Jetfine 3CA": NaN,
            "Add AO AO-24(\uc1a1\uc6d0)": 0.2,
            "Add MB NA-960": NaN,
            "Add MB 50%(PP base, L\uc0ac)": NaN,
            "Add MB NPK(16%, MI=50)": NaN,
            "Add MB \uc120\uc77c(3800 base)": NaN,
            "Add MB LA402XP(Adeka)": NaN,
            "Add MB DMG CF01(Wilmar, GMS95%, \uc11c\ud604\ud654\ud559)": NaN,
            "Add PA SLIP 250H": NaN,
            "Add PA FinaWax": NaN,
            "Add AO (1010+168)": NaN,
            "Add GMS": NaN
```



#### 물성 예측 리스트 (접속주소는 변동사항 있음)
물성예측 응답 시간은 1초이내로 확인되어 동기호출 가능

+ Request Header

Header Key | Value
---|---
Authorization |  Bearer u7ugIdt8LVUUTLRqigmHIPWjfjgCXyzL
Content-Type |  application/json

ID | 물성| 접속주소|
---|---|---|---
MI | MeltIndex | http://686b9f6f-ed7e-4272-a0a4-2fcfcd909501.westus.azurecontainer.io/score
I23 | Izod Impact 23 | http://225df43a-6f20-4ac2-a16c-1a942e66bb54.westus.azurecontainer.io/score
I30 | Izod Impact -30 | http://9b2ef751-a538-48a6-a58d-33a7bfe9f140.westus.azurecontainer.io/score
TS |TensileStrength	 | http://4b46ec9b-dce0-4df2-a823-8df0a92ce992.westus.azurecontainer.io/score
FM | FlexuralModulus | http://9db27d11-fdd9-4af4-95ba-d4a2febd4943.westus.azurecontainer.io/score









[Universal Model API POST Man Exporter Json download link](https://virtualrdsk.slack.com/files/U0193FNBCD9/F019CKU26FM/virtual_r_d.postman_collection.json)  

```
{
	"info": {
		"_postman_id": "3fca0d5d-e9cd-4413-97d5-3aef2c191d60",
		"name": "Virtual R&D",
		"description": "SKGC Virtual R&D Universal Model API Endpoint",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "MI_MODEL",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Authorization",
						"value": "Bearer IdC8sl79SRgGiRauXXxNyvhCnat4ju2C",
						"type": "text"
					},
					{
						"key": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"data\": [\n        {\n            \"Izod Impact 23\": NaN,\n            \"Izod Impact -30\": NaN,\n            \"TensileStrength\": NaN,\n            \"FlexuralModulus\": NaN,\n            \"PP H730F\": NaN,\n            \"PP B330F\": NaN,\n            \"PP BX3500\": NaN,\n            \"PP BX3800\": 10.0,\n            \"PP BX3900\": 46.0,\n            \"PP BX3910\": NaN,\n            \"PP BX3920\": NaN,\n            \"PP BX3950\": NaN,\n            \"PP HX3700\": NaN,\n            \"PP HX3800\": NaN,\n            \"PP HX3900\": NaN,\n            \"PP BH3820\": NaN,\n            \"POE Solumer 851\": 5.0,\n            \"POE Solumer 8605\": NaN,\n            \"POE Solumer 861\": NaN,\n            \"POE Solumer 865\": NaN,\n            \"POE Solumer 8613\": NaN,\n            \"POE Solumer 8705\": 5.0,\n            \"POE Solumer 871\": NaN,\n            \"POE Solumer 875\": 12.0,\n            \"POE Solumer 8730\": NaN,\n            \"POE Solumer 883\": NaN,\n            \"POE Solumer 891\": NaN,\n            \"Filler Wollastonite M-1250\": NaN,\n            \"Filler Whisker WS-1CY\": NaN,\n            \"Filler TALC KCM6300\": NaN,\n            \"Filler TALC 3000c\": 22.0,\n            \"Filler TALC Jetfine 3CA\": NaN,\n            \"Add AO AO-24(\\uc1a1\\uc6d0)\": 0.2,\n            \"Add MB NA-960\": NaN,\n            \"Add MB 50%(PP base, L\\uc0ac)\": NaN,\n            \"Add MB NPK(16%, MI=50)\": NaN,\n            \"Add MB \\uc120\\uc77c(3800 base)\": NaN,\n            \"Add MB LA402XP(Adeka)\": NaN,\n            \"Add MB DMG CF01(Wilmar, GMS95%, \\uc11c\\ud604\\ud654\\ud559)\": NaN,\n            \"Add PA SLIP 250H\": NaN,\n            \"Add PA FinaWax\": NaN,\n            \"Add AO (1010+168)\": NaN,\n            \"Add GMS\": NaN\n        }\n    ]\n}\n"
				},
				"url": {
					"raw": "http://686b9f6f-ed7e-4272-a0a4-2fcfcd909501.westus.azurecontainer.io/score",
					"protocol": "http",
					"host": [
						"686b9f6f-ed7e-4272-a0a4-2fcfcd909501",
						"westus",
						"azurecontainer",
						"io"
					],
					"path": [
						"score"
					]
				}
			},
			"response": []
		},
		{
			"name": "I23_MODEL",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Authorization",
						"value": "Bearer u7ugIdt8LVUUTLRqigmHIPWjfjgCXyzL",
						"type": "text"
					},
					{
						"key": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"data\": [\n        {\n            \"MeltIndex\": NaN,\n            \"Izod Impact -30\": NaN,\n            \"TensileStrength\": NaN,\n            \"FlexuralModulus\": NaN,\n            \"PP H730F\": NaN,\n            \"PP B330F\": NaN,\n            \"PP BX3500\": NaN,\n            \"PP BX3800\": NaN,\n            \"PP BX3900\": 50.0,\n            \"PP BX3910\": NaN,\n            \"PP BX3920\": 14.0,\n            \"PP BX3950\": NaN,\n            \"PP HX3700\": NaN,\n            \"PP HX3800\": NaN,\n            \"PP HX3900\": NaN,\n            \"PP BH3820\": NaN,\n            \"POE Solumer 851\": NaN,\n            \"POE Solumer 8605\": NaN,\n            \"POE Solumer 861\": NaN,\n            \"POE Solumer 865\": NaN,\n            \"POE Solumer 8613\": NaN,\n            \"POE Solumer 8705\": NaN,\n            \"POE Solumer 871\": NaN,\n            \"POE Solumer 875\": 20.0,\n            \"POE Solumer 8730\": NaN,\n            \"POE Solumer 883\": NaN,\n            \"POE Solumer 891\": NaN,\n            \"Filler Wollastonite M-1250\": NaN,\n            \"Filler Whisker WS-1CY\": NaN,\n            \"Filler TALC KCM6300\": 16.0,\n            \"Filler TALC 3000c\": NaN,\n            \"Filler TALC Jetfine 3CA\": NaN,\n            \"Add AO AO-24(\\uc1a1\\uc6d0)\": 0.2,\n            \"Add MB NA-960\": NaN,\n            \"Add MB 50%(PP base, L\\uc0ac)\": NaN,\n            \"Add MB NPK(16%, MI=50)\": NaN,\n            \"Add MB \\uc120\\uc77c(3800 base)\": NaN,\n            \"Add MB LA402XP(Adeka)\": NaN,\n            \"Add MB DMG CF01(Wilmar, GMS95%, \\uc11c\\ud604\\ud654\\ud559)\": NaN,\n            \"Add PA SLIP 250H\": NaN,\n            \"Add PA FinaWax\": NaN,\n            \"Add AO (1010+168)\": NaN,\n            \"Add GMS\": NaN\n        }\n    ]\n}\n"
				},
				"url": {
					"raw": "http://225df43a-6f20-4ac2-a16c-1a942e66bb54.westus.azurecontainer.io/score",
					"protocol": "http",
					"host": [
						"225df43a-6f20-4ac2-a16c-1a942e66bb54",
						"westus",
						"azurecontainer",
						"io"
					],
					"path": [
						"score"
					]
				}
			},
			"response": []
		},
		{
			"name": "I30_MODEL",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Authorization",
						"value": "Bearer hft6wqScXB4M5ZphvwxwahBYndmUCMM1",
						"type": "text"
					},
					{
						"key": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"data\": [\n        {\n            \"MeltIndex\": 20.2,\n            \"Izod Impact 23\": NaN,\n            \"TensileStrength\": NaN,\n            \"FlexuralModulus\": 1590.0,\n            \"PP H730F\": NaN,\n            \"PP B330F\": NaN,\n            \"PP BX3500\": NaN,\n            \"PP BX3800\": 10.0,\n            \"PP BX3900\": 46.0,\n            \"PP BX3910\": NaN,\n            \"PP BX3920\": NaN,\n            \"PP BX3950\": NaN,\n            \"PP HX3700\": NaN,\n            \"PP HX3800\": NaN,\n            \"PP HX3900\": NaN,\n            \"PP BH3820\": NaN,\n            \"POE Solumer 851\": 5.0,\n            \"POE Solumer 8605\": NaN,\n            \"POE Solumer 861\": NaN,\n            \"POE Solumer 865\": NaN,\n            \"POE Solumer 8613\": NaN,\n            \"POE Solumer 8705\": 5.0,\n            \"POE Solumer 871\": NaN,\n            \"POE Solumer 875\": 12.0,\n            \"POE Solumer 8730\": NaN,\n            \"POE Solumer 883\": NaN,\n            \"POE Solumer 891\": NaN,\n            \"Filler Wollastonite M-1250\": NaN,\n            \"Filler Whisker WS-1CY\": NaN,\n            \"Filler TALC KCM6300\": NaN,\n            \"Filler TALC 3000c\": 22.0,\n            \"Filler TALC Jetfine 3CA\": NaN,\n            \"Add AO AO-24(\\uc1a1\\uc6d0)\": 0.2,\n            \"Add MB NA-960\": NaN,\n            \"Add MB 50%(PP base, L\\uc0ac)\": NaN,\n            \"Add MB NPK(16%, MI=50)\": NaN,\n            \"Add MB \\uc120\\uc77c(3800 base)\": NaN,\n            \"Add MB LA402XP(Adeka)\": NaN,\n            \"Add MB DMG CF01(Wilmar, GMS95%, \\uc11c\\ud604\\ud654\\ud559)\": NaN,\n            \"Add PA SLIP 250H\": NaN,\n            \"Add PA FinaWax\": NaN,\n            \"Add AO (1010+168)\": NaN,\n            \"Add GMS\": NaN\n        }\n    ]\n}"
				},
				"url": {
					"raw": "http://9b2ef751-a538-48a6-a58d-33a7bfe9f140.westus.azurecontainer.io/score",
					"protocol": "http",
					"host": [
						"9b2ef751-a538-48a6-a58d-33a7bfe9f140",
						"westus",
						"azurecontainer",
						"io"
					],
					"path": [
						"score"
					]
				}
			},
			"response": []
		},
		{
			"name": "TS_MODEL",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Authorization",
						"value": "Bearer Bu4IA5dTrnYkYgAWJSzue8FrvHXP84b2",
						"type": "text"
					},
					{
						"key": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"data\": [\n        {\n            \"MeltIndex\": NaN,\n            \"Izod Impact 23\": NaN,\n            \"Izod Impact -30\": NaN,\n            \"FlexuralModulus\": NaN,\n            \"PP H730F\": NaN,\n            \"PP B330F\": NaN,\n            \"PP BX3500\": NaN,\n            \"PP BX3800\": NaN,\n            \"PP BX3900\": 50.0,\n            \"PP BX3910\": NaN,\n            \"PP BX3920\": 14.0,\n            \"PP BX3950\": NaN,\n            \"PP HX3700\": NaN,\n            \"PP HX3800\": NaN,\n            \"PP HX3900\": NaN,\n            \"PP BH3820\": NaN,\n            \"POE Solumer 851\": NaN,\n            \"POE Solumer 8605\": NaN,\n            \"POE Solumer 861\": NaN,\n            \"POE Solumer 865\": NaN,\n            \"POE Solumer 8613\": NaN,\n            \"POE Solumer 8705\": NaN,\n            \"POE Solumer 871\": NaN,\n            \"POE Solumer 875\": 20.0,\n            \"POE Solumer 8730\": NaN,\n            \"POE Solumer 883\": NaN,\n            \"POE Solumer 891\": NaN,\n            \"Filler Wollastonite M-1250\": NaN,\n            \"Filler Whisker WS-1CY\": NaN,\n            \"Filler TALC KCM6300\": 16.0,\n            \"Filler TALC 3000c\": NaN,\n            \"Filler TALC Jetfine 3CA\": NaN,\n            \"Add AO AO-24(\\uc1a1\\uc6d0)\": 0.2,\n            \"Add MB NA-960\": NaN,\n            \"Add MB 50%(PP base, L\\uc0ac)\": NaN,\n            \"Add MB NPK(16%, MI=50)\": NaN,\n            \"Add MB \\uc120\\uc77c(3800 base)\": NaN,\n            \"Add MB LA402XP(Adeka)\": NaN,\n            \"Add MB DMG CF01(Wilmar, GMS95%, \\uc11c\\ud604\\ud654\\ud559)\": NaN,\n            \"Add PA SLIP 250H\": NaN,\n            \"Add PA FinaWax\": NaN,\n            \"Add AO (1010+168)\": NaN,\n            \"Add GMS\": NaN\n        }\n    ]\n}"
				},
				"url": {
					"raw": "http://4b46ec9b-dce0-4df2-a823-8df0a92ce992.westus.azurecontainer.io/score",
					"protocol": "http",
					"host": [
						"4b46ec9b-dce0-4df2-a823-8df0a92ce992",
						"westus",
						"azurecontainer",
						"io"
					],
					"path": [
						"score"
					]
				}
			},
			"response": []
		},
		{
			"name": "FM_MODEL",
			"request": {
				"method": "POST",
				"header": [
					{
						"key": "Authorization",
						"value": "Bearer c3mqsjkN5GIkaFBaoP6Us6YuKOhBb6R9",
						"type": "text"
					},
					{
						"key": "Content-Type",
						"value": "application/json",
						"type": "text"
					}
				],
				"body": {
					"mode": "raw",
					"raw": "{\n    \"data\": [\n        {\n            \"MeltIndex\": NaN,\n            \"Izod Impact 23\": NaN,\n            \"Izod Impact -30\": NaN,\n            \"TensileStrength\": NaN,\n            \"PP H730F\": NaN,\n            \"PP B330F\": NaN,\n            \"PP BX3500\": NaN,\n            \"PP BX3800\": 10.0,\n            \"PP BX3900\": 46.0,\n            \"PP BX3910\": NaN,\n            \"PP BX3920\": NaN,\n            \"PP BX3950\": NaN,\n            \"PP HX3700\": NaN,\n            \"PP HX3800\": NaN,\n            \"PP HX3900\": NaN,\n            \"PP BH3820\": NaN,\n            \"POE Solumer 851\": 5.0,\n            \"POE Solumer 8605\": NaN,\n            \"POE Solumer 861\": NaN,\n            \"POE Solumer 865\": NaN,\n            \"POE Solumer 8613\": NaN,\n            \"POE Solumer 8705\": 5.0,\n            \"POE Solumer 871\": NaN,\n            \"POE Solumer 875\": 12.0,\n            \"POE Solumer 8730\": NaN,\n            \"POE Solumer 883\": NaN,\n            \"POE Solumer 891\": NaN,\n            \"Filler Wollastonite M-1250\": NaN,\n            \"Filler Whisker WS-1CY\": NaN,\n            \"Filler TALC KCM6300\": NaN,\n            \"Filler TALC 3000c\": 22.0,\n            \"Filler TALC Jetfine 3CA\": NaN,\n            \"Add AO AO-24(\\uc1a1\\uc6d0)\": 0.2,\n            \"Add MB NA-960\": NaN,\n            \"Add MB 50%(PP base, L\\uc0ac)\": NaN,\n            \"Add MB NPK(16%, MI=50)\": NaN,\n            \"Add MB \\uc120\\uc77c(3800 base)\": NaN,\n            \"Add MB LA402XP(Adeka)\": NaN,\n            \"Add MB DMG CF01(Wilmar, GMS95%, \\uc11c\\ud604\\ud654\\ud559)\": NaN,\n            \"Add PA SLIP 250H\": NaN,\n            \"Add PA FinaWax\": NaN,\n            \"Add AO (1010+168)\": NaN,\n            \"Add GMS\": NaN\n        }\n    ]\n}"
				},
				"url": {
					"raw": "http://9db27d11-fdd9-4af4-95ba-d4a2febd4943.westus.azurecontainer.io/score",
					"protocol": "http",
					"host": [
						"9db27d11-fdd9-4af4-95ba-d4a2febd4943",
						"westus",
						"azurecontainer",
						"io"
					],
					"path": [
						"score"
					]
				}
			},
			"response": []
		}
	],
	"protocolProfileBehavior": {}
}
```
