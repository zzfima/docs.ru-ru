---
title: Свойство SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c586d07e8ea0c2ac0b1efb603e8900d681fd0a91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152667"
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