---
title: Метод SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c7199cbd08e62b1f0391437a0c1864cb9036fe1f
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222709"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>Метод SqlStreamChars.SetLength(Int64)

При переопределении в производном классе, освобождает ресурсы, используемые в поток. Дружественные сборки, содержащей этот метод связан с SQLAccess.dll. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Параметры

`value`\
Нужная длина текущего потока в байтах.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.SetLength` Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.