---
title: Метод SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d52a1cd4dd70c29fc1af3fcf50c4f9b0c90125df
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827387"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Метод SqlStreamChars.Seek (Int64, SeekOrigin)

При переопределении в производном классе задает позицию в текущем потоке. Дружественные сборки, содержащей этот метод связан с SQLAccess.dll. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Параметры

`offset`\
Смещение в байтах относительно `origin`.

`origin`\
Одно из значений перечисления, указывающее опорную точку для получения новой позиции.

## <a name="returns"></a>Returns

<xref:System.Int32>\
Новая позиция в текущем потоке.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.Seek` Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.