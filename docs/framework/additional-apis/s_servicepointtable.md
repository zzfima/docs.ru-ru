---
title: ServicePointManager. s_ServicePointTable, поле
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120001"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager. s\_поле Сервицепоинттабле

`ServicePointManager.s_ServicePointTable` — это <xref:System.Collections.Hashtable>, содержащий список активных HTTP-подключений (<xref:System.Net.ServicePoint>s) в <xref:System.AppDomain>.

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Поле `ServicePointManager.s_ServicePointTable` является закрытым и не предназначено для непосредственного использования в коде.
> 
> Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System. dll)

**.NET Framework версии:** Доступно с 2,0.
