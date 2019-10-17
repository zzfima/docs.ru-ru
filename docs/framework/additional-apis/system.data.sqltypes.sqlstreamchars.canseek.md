---
title: Свойство Склстреамчарс. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395778"
---
# <a name="sqlstreamcharscanseek-property"></a>Склстреамчарс. CanSeek, свойство

При переопределении в производном классе получает значение, указывающее, поддерживает ли текущий Steam операцию Seek. Сборка, содержащая это свойство, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Boolean>\
`true`, если текущий Steam поддерживает операцию Seek; в противном случае `false`.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Свойство `SqlStreamChars.CanSeek` является закрытым и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
