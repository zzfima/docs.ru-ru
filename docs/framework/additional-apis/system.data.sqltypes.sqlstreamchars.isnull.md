---
title: Свойство SqlStreamChars.IsNull (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 79ebb9ec54185a94cb95dfd0fb2929e61cf513ef
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152627"
---
# <a name="sqlstreamcharsisnull-property"></a>Свойство SqlStreamChars.IsNull

При переопределении в производном классе получает значение, указывающее, является ли поток `null`. Сборка, содержащая это свойство имеет с SQLAccess.dll связью. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

## <a name="syntax"></a>Синтаксис

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Boolean>\
`true` Если поток `null`; в противном случае `false`.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SqlStreamChars.IsNull` Свойство является закрытым и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Data.SqlTypes>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.