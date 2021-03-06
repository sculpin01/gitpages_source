---
title: 세계 조류(World Tide)
description: Instructions on how to add Tides information to Home Assistant.
logo: worldtidesinfo.png
ha_category:
  - Environment
ha_release: 0.52
---

<div class='videoWrapper'>
<iframe width="690" height="437" src="https://www.youtube.com/embed/sHCTH3tPEJM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

`worldtidesinfo` 센서 플랫폼은 [World Tides](https://www.worldtides.info/)의 세부 정보를 사용하여 전세계 모든 위치에 대한 조류 예측 정보를 제공합니다.


## 셋업 

[https://www.worldtides.info/](https://www.worldtides.info/)의 계정에서 API 키를 받으십시오.

## 설정

이 센서를 사용하려면`configuration.yaml` 파일에 다음을 추가하십시오

```yaml
# Example configuration.yaml entry
sensor:
  - platform: worldtidesinfo
    api_key: YOUR_API_KEY
```

{% configuration %}
api_key:
  description: API 키.
  required: true
  type: string
name:
  description: 프론트 엔드에서 사용할 이름.
  required: false
  type: string
  default: WorldTidesInfo
latitude:
  description: 조수를 표시할 위치의 위도.
  required: false
  type: float
  default: "The latitude in your `configuration.yaml` file."
longitude:
  description: 조수를 표시할 위치의 경도.
  required: false
  type: float
  default: "The longitude in your `configuration.yaml` file."
{% endconfiguration %}
