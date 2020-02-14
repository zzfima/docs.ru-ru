---
title: Метод Message. Вритестарсеадерс (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214867"
---
# <a name="messagewritestartheaders-method"></a>Метод Message. Вритестарсеадерс

Записывает начальный заголовок в XML-файл путем вызова метода <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Параметры

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Модуль записи, используемый для записи начального заголовка в XML-файл.

## <a name="remarks"></a>Примечания

> [!WARNING]
> Метод `Message.WriteStartHeaders` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.ServiceModel.Channels>

**Сборка:** System. ServiceModel. dll

**.NET Framework версии:** Доступно с 3,0.
