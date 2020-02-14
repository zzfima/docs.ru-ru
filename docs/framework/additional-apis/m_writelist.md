---
title: Поле Connection. m_WriteList
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
ms.openlocfilehash: 22f939d13cceac4d1c0b39e9e8fe20cdc0ab9387
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214901"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="a7156-102">Connection. m\_поле Врителист</span><span class="sxs-lookup"><span data-stu-id="a7156-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="a7156-103">`Connection.m_WriteList` — это <xref:System.Collections.ArrayList> <xref:System.Net.HttpWebRequest> объектов, которые помещаются в очередь для отправки по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a7156-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7156-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7156-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="a7156-105">Поле `Connection.m_WriteList` является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="a7156-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="a7156-106">Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="a7156-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7156-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a7156-107">Requirements</span></span>

<span data-ttu-id="a7156-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a7156-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a7156-109">**Сборка:** Система (в System. dll)</span><span class="sxs-lookup"><span data-stu-id="a7156-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a7156-110">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="a7156-110">**.NET Framework versions:** Available since 2.0.</span></span>
