---
title: Метод Склстреамчарс. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395596"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="35ae9-102">Метод Склстреамчарс. Seek (Int64, SeekOrigin)</span><span class="sxs-lookup"><span data-stu-id="35ae9-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="35ae9-103">При переопределении в производном классе задает позицию в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="35ae9-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="35ae9-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="35ae9-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="35ae9-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35ae9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="35ae9-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="35ae9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="35ae9-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="35ae9-107">Parameters</span></span>

`offset`\
<span data-ttu-id="35ae9-108">Смещение в байтах относительно `origin`.</span><span class="sxs-lookup"><span data-stu-id="35ae9-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="35ae9-109">Одно из значений перечисления, указывающее точку ссылки, из которой следует получить новую позицию.</span><span class="sxs-lookup"><span data-stu-id="35ae9-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="35ae9-110">Returns</span><span class="sxs-lookup"><span data-stu-id="35ae9-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="35ae9-111">Новая позиция в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="35ae9-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="35ae9-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="35ae9-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="35ae9-113">Метод `SqlStreamChars.Seek` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="35ae9-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="35ae9-114">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="35ae9-114">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="35ae9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="35ae9-115">Requirements</span></span>

<span data-ttu-id="35ae9-116">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="35ae9-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="35ae9-117">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="35ae9-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="35ae9-118">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="35ae9-118">**.NET Framework versions:** Available since 2.0.</span></span>
