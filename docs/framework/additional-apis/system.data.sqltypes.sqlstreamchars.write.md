---
title: Метод Склстреамчарс. Write (char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395579"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>Метод Склстреамчарс. Write (char [], Int32, Int32)

При переопределении в производном классе записывает последовательность символов в текущий поток и перемещает текущую позицию в этом потоке вперед на число записанных символов. Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll. Он предназначен для использования SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Параметры

`buffer`  
Массив символов для записи.

`offset`  
Смещение относительно начала координат.

`count`  
Число символов, записываемых в текущий поток.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `SqlStreamChars.Write` является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода для написания в рабочем приложении каких-либо обстоятельств.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System. Data (в System. Data. dll)

**.NET Framework версии:** Доступно с 2,0.
