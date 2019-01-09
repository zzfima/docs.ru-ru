---
title: Поле Connection.m_WriteList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: a7446b9cbbfd4d3a4d38368a8e24c99527cf9108
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146710"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="e2058-102">Connection.m\_WriteList поля</span><span class="sxs-lookup"><span data-stu-id="e2058-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="e2058-103">`Connection.m_WriteList` — <xref:System.Collections.ArrayList> из <xref:System.Net.HttpWebRequest> объекты, которые становятся в очередь для передачи по HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2058-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2058-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2058-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="e2058-105">`Connection.m_WriteList` Поле является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="e2058-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="e2058-106">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="e2058-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2058-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e2058-107">Requirements</span></span>

<span data-ttu-id="e2058-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e2058-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e2058-109">**Сборка:** Системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="e2058-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e2058-110">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="e2058-110">**.NET Framework versions:** Available since 2.0.</span></span>
