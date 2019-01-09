---
title: Метод SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3f2180d9a1893e651f174fff6d0f073df651e712
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152567"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a>Метод SqlStreamChars.Dispose(Boolean)

При переопределении в производном классе, освобождает ресурсы, используемые в поток. Дружественные сборки, содержащей этот метод связан с SQLAccess.dll. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a>Параметры

`disposing`\
Значение `true` позволяет освободить как управляемые, так и неуправляемые ресурсы; значение `false` освобождает только неуправляемые ресурсы.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.Dispose` Метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.