---
title: Склстреамчарс. length, свойство (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395605"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="2050f-102">Склстреамчарс. length, свойство</span><span class="sxs-lookup"><span data-stu-id="2050f-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="2050f-103">При переопределении в производном классе получает длину текущего потока.</span><span class="sxs-lookup"><span data-stu-id="2050f-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="2050f-104">Сборка, содержащая это свойство, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="2050f-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2050f-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2050f-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2050f-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="2050f-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="2050f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2050f-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="2050f-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="2050f-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="2050f-109">Длина потока.</span><span class="sxs-lookup"><span data-stu-id="2050f-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="2050f-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2050f-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2050f-111">Свойство `SqlStreamChars.Length` является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="2050f-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2050f-112">Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="2050f-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2050f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2050f-113">Requirements</span></span>

<span data-ttu-id="2050f-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2050f-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2050f-115">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="2050f-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2050f-116">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="2050f-116">**.NET Framework versions:** Available since 2.0.</span></span>
