---
title: Метод Message. Вритестарсеадерс (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451290"
---
# <a name="messagewritestartheaders-method"></a>Метод Message. Вритестарсеадерс

Записывает начальный заголовок в XML-файл путем вызова метода <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Параметры

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Модуль записи, используемый для записи начального заголовка в XML-файл.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `Message.WriteStartHeaders` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.ServiceModel.Channels>

**Сборка:** System. ServiceModel. dll

**.NET Framework версии:** Доступно с 3,0.
