---
title: Метод SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152537"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>Метод SqlStreamChars.Read (Char [], Int32, Int32)

При переопределении в производном классе, считывает следующий набор символов из входного потока. Дружественные сборки, содержащей этот метод связан с SQLAccess.dll. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Параметры

`buffer`\
Массива символов для чтения.

`offset`\
Смещение относительно начала координат.

`count`\
Число символов для чтения из текущего потока.

## <a name="returns"></a>Returns

<xref:System.Int32>\
Общее количество символов, считанных в буфер.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.Read` Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.