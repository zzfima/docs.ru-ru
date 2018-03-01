---
title: "Поле ServicePointManager.s_ServicePointTable"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8dfdbab78d8efab13487575218820f8b0455248d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable поля

`ServicePointManager.s_ServicePointTable`— <xref:System.Collections.Hashtable> , содержащая список активных подключений HTTP (<xref:System.Net.ServicePoint>s) в <xref:System.AppDomain>.

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable` Поля является закрытым и не предназначены для непосредственного использования в коде.
> 
> Корпорация Майкрософт не поддерживает использование этого поля в реальном приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:**<xref:System.Net>

**Сборка:** системы (в System.dll)

**Версии платформы .NET framework:** доступно с версии 2.0.
