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
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743164"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="5e103-102">Connection.m\_WriteList поля</span><span class="sxs-lookup"><span data-stu-id="5e103-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="5e103-103">`Connection.m_WriteList` — <xref:System.Collections.ArrayList> из <xref:System.Net.HttpWebRequest> объекты, которые помещаются в очередь копирование отправляться по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="5e103-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e103-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e103-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="5e103-105">`Connection.m_WriteList` Поля является закрытым и не предназначены для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="5e103-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="5e103-106">Корпорация Майкрософт не поддерживает использование этого поля в реальном приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="5e103-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e103-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5e103-107">Requirements</span></span>

<span data-ttu-id="5e103-108">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5e103-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5e103-109">**Сборка:** системы (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="5e103-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5e103-110">**Версии платформы .NET framework:** доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="5e103-110">**.NET Framework versions:** Available since 2.0.</span></span>
