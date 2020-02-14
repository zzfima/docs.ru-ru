---
title: Метод Exception. Препфорремотинг (система)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214889"
---
# <a name="exceptionprepforremoting-method"></a>Метод Exception.PrepForRemoting

Сохраняет трассировку стека на стороне сервера, добавляя ее к сообщению, прежде чем исключение будет повторно создано на сайте вызова клиента.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Результаты

<xref:System.Exception>  
Данный экземпляр <xref:System.Exception>.

## <a name="remarks"></a>Примечания

> [!WARNING]
> Метод `Exception.PrepForRemoting` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System>

**Сборка:** mscorlib. dll (в mscorlib. dll)

**.NET Framework версии:** Доступно с 1,0.
