---
title: Свойство SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634002"
---
# <a name="sqlcharsstream-property"></a>Свойство SqlChars.Stream

Возвращает или задает поток символов. Сборка, содержащая это свойство имеет с SQLAccess.dll связью. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a>Значение свойства

`System.Data.SqlTypes.SqlStreamChars`\
Поток символов.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlChars.Stream` Свойство является внутренним и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого свойства в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.