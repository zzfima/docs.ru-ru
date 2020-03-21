---
title: ServicePointManager.s_ServicePointTable Field
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155821"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager.s\_ServicePointTable поле

`ServicePointManager.s_ServicePointTable`является, <xref:System.Collections.Hashtable> который содержит список активных соединений HTTP (s)<xref:System.Net.ServicePoint>в . <xref:System.AppDomain>

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Поле `ServicePointManager.s_ServicePointTable` является частным и не предназначено для использования непосредственно в коде.
>
> Корпорация Майкрософт ни при каких обстоятельствах не поддерживает использование этого поля в производственном приложении.

## <a name="requirements"></a>Требования

**Пространство имен:**<xref:System.Net>

**Сборка:** Система (в System.dll)

**Рамочные версии .NET:** Доступно с 2.0.
