---
title: 룸바 로봇청소기(irobot Roomba)
description: Instructions on how to integrate your Wi-Fi enabled Roomba within Home Assistant.
logo: irobot_roomba.png
ha_category:
  - Vacuum
ha_release: 0.51
ha_codeowners:
  - '@pschmitt'
---

<div class='videoWrapper'>
<iframe width="690" height="437" src="https://www.youtube.com/embed/dTzBa0UhQo0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

`roomba` 통합구성요소를 통해 [iRobot Roomba](https://www.irobot.com/For-the-Home/Vacuuming/Roomba.aspx) vacuum(로봇청소기)을 제어할 수 있습니다.

<p class='img'>
<img src='/images/screenshots/more-info-dialog-roomba.png' />
</p>

<div class='note'>
이 플랫폼은 테스트를 거쳐 iRobot Roomba 980 및 890 모델과 작동하는 것으로 확인되었지만 690 또는 960과 같은 Wi-Fi 지원 Roomba에서도 잘 작동합니다.
</div>

## 설정

Roomba vacuum을 설치에 추가하려면 `configuration.yaml` 파일에 다음을 추가하십시오.

```yaml
# Example configuration.yaml entry
vacuum:
  - platform: roomba
    host: IP_ADDRESS_OR_HOSTNAME
    username: BLID
    password: PASSWORD
```

{% configuration %}
host:
  description: The hostname or IP address of the Roomba.
  required: true
  type: string
username:
  description: The username (BLID) for your device.
  required: true
  type: string
password:
  description: The password for your device.
  required: true
  type: string
name:
  description: The name of the vacuum.
  required: false
  type: string
  default: Roomba
certificate:
  description: Path to your certificate store.
  required: false
  type: string
  default: /etc/ssl/certs/ca-certificates.crt
continuous:
  description: Whether to operate in continuous mode.
  required: false
  type: boolean
  default: true
delay:
  description: Custom connection delay (in seconds) for periodic mode
  required: false
  type: integer
  default: 1
{% endconfiguration %}

<div class='note'>

Roomba의 MQTT 서버는 단일 연결만 허용합니다. 연속 모드를 활성화하면 클라우드를 통해 앱이 Roomba에 연결됩니다. [More info here](https://github.com/NickWaterton/Roomba980-Python#firmware-2xx-notes)

</div>

### Retrieving your credentials

BLID (사용자 이름)와 비밀번호를 모두 검색하려면 [여기](https://github.com/NickWaterton/Roomba980-Python#how-to-get-your-usernameblid-and-password) 또는 [여기](https://github.com/koalazak/dorita980#how-to-get-your-usernameblid-and-password)를 참조하십시오.