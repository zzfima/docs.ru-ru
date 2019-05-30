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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d06968c844dc9187b973af156a29ded9ba7cde66
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301398"
---
# <a name="connectiongroupmconnectionlist-field"></a><span data-ttu-id="074ce-102">ConnectionGroup.m\_ConnectionList поля</span><span class="sxs-lookup"><span data-stu-id="074ce-102">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="074ce-103">`ConnectionGroup.m_ConnectionList` является <xref:System.Collections.ArrayList> объектов подключения, обслуживаемые одним и тем же URI и общего ресурса одинаковые значения для некоторых других свойств, такие как срок действия и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="074ce-103">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="074ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="074ce-104">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="074ce-105">`ConnectionGroup.m_ConnectionList` Поле является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="074ce-105">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="074ce-106">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="074ce-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="074ce-107">Требования</span><span class="sxs-lookup"><span data-stu-id="074ce-107">Requirements</span></span>

<span data-ttu-id="074ce-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="074ce-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="074ce-109">**Сборка:** Системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="074ce-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="074ce-110">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="074ce-110">**.NET Framework versions:** Available since 2.0.</span></span>
