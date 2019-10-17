---
title: Метод Склстреамчарс. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395724"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>Склстреамчарс. SetLength (Int64), метод

При переопределении в производном классе освобождает ресурсы, используемые потоком. Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Параметры

`value`\
Нужная длина текущего потока в байтах.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `SqlStreamChars.SetLength` является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
