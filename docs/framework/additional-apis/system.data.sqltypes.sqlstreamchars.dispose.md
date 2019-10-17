---
title: Метод Склстреамчарс. Dispose (Boolean) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 44dc97835b8a7141064e8de4d2d5325c40be5a34
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395766"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="c97a5-102">Метод Склстреамчарс. Dispose (логический)</span><span class="sxs-lookup"><span data-stu-id="c97a5-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="c97a5-103">При переопределении в производном классе освобождает ресурсы, используемые потоком.</span><span class="sxs-lookup"><span data-stu-id="c97a5-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="c97a5-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="c97a5-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c97a5-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c97a5-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c97a5-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="c97a5-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="c97a5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c97a5-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="c97a5-108">Значение `true` позволяет освободить как управляемые, так и неуправляемые ресурсы; значение `false` освобождает только неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="c97a5-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="c97a5-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c97a5-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c97a5-110">Метод `SqlStreamChars.Dispose` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="c97a5-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c97a5-111">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="c97a5-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c97a5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c97a5-112">Requirements</span></span>

<span data-ttu-id="c97a5-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c97a5-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c97a5-114">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="c97a5-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c97a5-115">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="c97a5-115">**.NET Framework versions:** Available since 2.0.</span></span>
