---
title: Свойство Склстреамчарс. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395778"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="9bc6e-102">Склстреамчарс. CanSeek, свойство</span><span class="sxs-lookup"><span data-stu-id="9bc6e-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="9bc6e-103">При переопределении в производном классе получает значение, указывающее, поддерживает ли текущий Steam операцию Seek.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="9bc6e-104">Сборка, содержащая это свойство, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="9bc6e-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="9bc6e-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="9bc6e-107">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="9bc6e-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="9bc6e-108">`true`, если текущий Steam поддерживает операцию Seek; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9bc6e-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="9bc6e-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="9bc6e-110">Свойство `SqlStreamChars.CanSeek` является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9bc6e-111">Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9bc6e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9bc6e-112">Requirements</span></span>

<span data-ttu-id="9bc6e-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="9bc6e-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="9bc6e-114">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="9bc6e-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="9bc6e-115">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="9bc6e-115">**.NET Framework versions:** Available since 2.0.</span></span>
