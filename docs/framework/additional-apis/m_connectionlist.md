---
title: Поле ConnectionGroup.m_ConnectionList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
author: guardrex
ms.author: mairaw
ms.openlocfilehash: c9162e123c1167e3aa1be26ddd37279c088acc89
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149167"
---
# <a name="connectiongroupmconnectionlist-field"></a><span data-ttu-id="82335-102">ConnectionGroup.m\_ConnectionList поля</span><span class="sxs-lookup"><span data-stu-id="82335-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="82335-103">`ConnectionGroup.m_ConnectionList` является <xref:System.Collections.ArrayList> объектов подключения, обслуживаемые одним и тем же URI и общего ресурса одинаковые значения для некоторых других свойств, такие как срок действия и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="82335-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="82335-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82335-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="82335-105">`ConnectionGroup.m_ConnectionList` Поле является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="82335-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="82335-106">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="82335-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="82335-107">Требования</span><span class="sxs-lookup"><span data-stu-id="82335-107">Requirements</span></span>

<span data-ttu-id="82335-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="82335-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="82335-109">**Сборка:** Системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="82335-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="82335-110">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="82335-110">**.NET Framework versions:** Available since 2.0.</span></span>
