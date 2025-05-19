---
id: device
title: Dados do celular
---

## Método

#### /Status

`GET` https://app.plugchat.com.br/api/whatsapp/device

## Header
#### Toda requisição http feita precisa passar sua header de autorização.


| Key            | Value                   |
| :------------: |   :---------------:     |
| Authorization: |   1nEFbU3EktLnV7LIIzX   |

---

## Conceituação

Este método é responsável por retornar informações sobre o device/celular conectado

---

## Atributos

```json
{
  "phone": "",
  "imgUrl": null,
  "device": {
    "wa_version": "2.21.10.16",
    "mcc": "724",
    "mnc": "039",
    "os_version": "7.1.2",
    "device_manufacturer": "samsung",
    "device_model": "SM-N975F",
    "osbuildnumber": "samsung-user 7.1.2 20171130.276299 release-keys",
    "platform": "smba"
  }
}
```

---

## Code

<iframe src="//api.apiembed.com/?source=https://raw.githubusercontent.com/fourpixelit/plug-chat-docs/main/json-examples/device.json&targets=all" frameborder="0" scrolling="no" width="100%" height="500px" seamless></iframe>
