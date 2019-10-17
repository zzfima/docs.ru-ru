---
title: Метод Склстреамчарс. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395596"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Метод Склстреамчарс. Seek (Int64, SeekOrigin)

При переопределении в производном классе задает позицию в текущем потоке. Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Параметры

`offset`\
Смещение в байтах относительно `origin`.

`origin`\
Одно из значений перечисления, указывающее точку ссылки, из которой следует получить новую позицию.

## <a name="returns"></a>Returns

<xref:System.Int32>\
Новая позиция в текущем потоке.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `SqlStreamChars.Seek` является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
