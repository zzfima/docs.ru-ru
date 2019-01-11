---
title: Свойство SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5453167e16e2658b3546b7114201b04d481a0c79
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223018"
---
# <a name="smiorderpropertyitem-property"></a>Свойство SmiOrderProperty.Item

Получает порядок столбцов для сущности. Сборка, содержащая это свойство имеет с SQLAccess.dll связью. Он предназначен для использования с SQL Server. Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.

## <a name="syntax"></a>Синтаксис

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a>Значение свойства

Порядок столбцов.

## <a name="remarks"></a>Примечания

> [!WARNING]
> `SmiOrderProperty.Item` Свойство является внутренним и не предназначен для непосредственного использования в коде.
>
> Майкрософт не поддерживает использование этого свойства в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:Microsoft.SqlServer.Server>

**Сборка:** System.Data (в System.Data.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.