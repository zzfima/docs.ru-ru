---
title: Метод Склстреамчарс. Flush (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395615"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="eb201-102">Склстреамчарс. Flush, метод</span><span class="sxs-lookup"><span data-stu-id="eb201-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="eb201-103">При переопределении в производном классе очищает все буферы данного потока и вызывает запись данных буферов в базовое устройство.</span><span class="sxs-lookup"><span data-stu-id="eb201-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="eb201-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="eb201-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="eb201-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb201-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="eb201-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="eb201-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb201-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb201-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="eb201-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="eb201-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="eb201-109">Метод `SqlStreamChars.Flush` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="eb201-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="eb201-110">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="eb201-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb201-111">Требования</span><span class="sxs-lookup"><span data-stu-id="eb201-111">Requirements</span></span>

<span data-ttu-id="eb201-112">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="eb201-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="eb201-113">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="eb201-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="eb201-114">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="eb201-114">**.NET Framework versions:** Available since 2.0.</span></span>
