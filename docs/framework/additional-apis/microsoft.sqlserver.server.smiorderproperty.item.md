---
title: Свойство SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
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
ms.openlocfilehash: cb2f6cb956f9571f9bd2ba7f86d79c5df6e72a15
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827738"
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