---
title: Поле ServicePointManager.s_ServicePointTable
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301388"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="3c522-102">ServicePointManager.s\_ServicePointTable поля</span><span class="sxs-lookup"><span data-stu-id="3c522-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="3c522-103">`ServicePointManager.s_ServicePointTable` — <xref:System.Collections.Hashtable> , содержащий список активных подключений HTTP (<xref:System.Net.ServicePoint>s) в <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="3c522-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c522-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c522-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="3c522-105">`ServicePointManager.s_ServicePointTable` Поле является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="3c522-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="3c522-106">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="3c522-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c522-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3c522-107">Requirements</span></span>

<span data-ttu-id="3c522-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3c522-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3c522-109">**Сборка:** Системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="3c522-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="3c522-110">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="3c522-110">**.NET Framework versions:** Available since 2.0.</span></span>
