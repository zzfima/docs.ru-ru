---
title: Метод Склстреамчарс. Flush (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395615"
---
# <a name="sqlstreamcharsflush-method"></a>Склстреамчарс. Flush, метод

При переопределении в производном классе очищает все буферы данного потока и вызывает запись данных буферов в базовое устройство. Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

## <a name="syntax"></a>Синтаксис

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `SqlStreamChars.Flush` является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
