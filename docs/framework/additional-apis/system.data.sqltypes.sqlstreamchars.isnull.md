---
title: Свойство Склстреамчарс. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395734"
---
# <a name="sqlstreamcharsisnull-property"></a>Склстреамчарс. IsNull, свойство

При переопределении в производном классе получает значение, указывающее, является ли поток `null`. Сборка, содержащая это свойство, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

## <a name="syntax"></a>Синтаксис

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Boolean>\
`true`, если поток `null`; в противном случае `false`.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Свойство `SqlStreamChars.IsNull` является закрытым и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
