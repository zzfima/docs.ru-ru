---
title: Метод MemoryStream. Интерналжеторигинандленгс (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215464"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>Метод MemoryStream. Интерналжеторигинандленгс

Возвращает внутренние значения источника и длину потока памяти.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Параметры

- `origin` <xref:System.Int32>\
  При возврате из этого метода смещение массива байтов, указанного при создании нового объекта <xref:System.IO.MemoryStream>. Содержит 0, если массив байтов был создан <xref:System.IO.MemoryStream>.

- `length` <xref:System.Int32>\
  При возврате из этого метода число байтов в потоке памяти.

## <a name="remarks"></a>Примечания

> [!WARNING]
> Метод `MemoryStream.InternalGetOriginAndLength` является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.IO>

**Сборка:** mscorlib. dll (в mscorlib. dll)

**.NET Framework версии:** Доступно с 2,0.
