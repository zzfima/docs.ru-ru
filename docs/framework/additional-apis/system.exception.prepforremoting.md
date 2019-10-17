---
title: Метод Exception. Препфорремотинг (система)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405900"
---
# <a name="exceptionprepforremoting-method"></a>Метод Exception. Препфорремотинг

Сохраняет трассировку стека на стороне сервера, добавляя ее к сообщению, прежде чем исключение будет повторно создано на сайте вызова клиента.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Returns

<xref:System.Exception>  
Данный экземпляр <xref:System.Exception>.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Метод `Exception.PrepForRemoting` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System>

**Сборка:** mscorlib. dll (в mscorlib. dll)

**.NET Framework версии:** Доступно с 1,0.
