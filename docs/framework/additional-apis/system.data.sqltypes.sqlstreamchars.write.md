---
title: SqlStreamChars.Write(Char[], Int32, Int32) Method (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2b0d2c4e68ffa0c0b9e745a15dbb8c79659008c
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826035"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>Метод SqlStreamChars.Write (Char [], Int32, Int32)

При переопределении в производном классе, записывает последовательность символов в текущий поток и перемещает текущую позицию внутри потока на число записанных символов. Дружественные сборки, содержащей этот метод связан с SQLAccess.dll. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Параметры

`buffer`  
Записываемый массив char.

`offset`  
Смещение относительно начала координат.

`count`  
Число символов для записи в текущий поток.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.Write` Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.