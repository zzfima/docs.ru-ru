---
title: Метод Склстреамчарс. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395724"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="3bc0c-102">Склстреамчарс. SetLength (Int64), метод</span><span class="sxs-lookup"><span data-stu-id="3bc0c-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="3bc0c-103">При переопределении в производном классе освобождает ресурсы, используемые потоком.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="3bc0c-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3bc0c-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="3bc0c-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="3bc0c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bc0c-107">Parameters</span></span>

`value`\
<span data-ttu-id="3bc0c-108">Нужная длина текущего потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bc0c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3bc0c-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3bc0c-110">Метод `SqlStreamChars.SetLength` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3bc0c-111">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bc0c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3bc0c-112">Requirements</span></span>

<span data-ttu-id="3bc0c-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3bc0c-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3bc0c-114">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="3bc0c-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3bc0c-115">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="3bc0c-115">**.NET Framework versions:** Available since 2.0.</span></span>
