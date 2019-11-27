---
title: Метод Message. Бодитостринг (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 7b0b56bfda1c0c37f43f95e9684d3b4042c1b97c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451314"
---
# <a name="messagebodytostring-method"></a>Метод Message. Бодитостринг

Преобразует текст сообщения в строку путем вызова метода <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Параметры

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Модуль записи, используемый для преобразования тела сообщения в строку.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `Message.BodyToString` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.ServiceModel.Channels>

**Сборка:** System. ServiceModel. dll

**.NET Framework версии:** Доступно с 3,0.
