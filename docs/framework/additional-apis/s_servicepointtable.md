---
title: Поле ServicePointManager. s_ServicePointTable
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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214922"
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
