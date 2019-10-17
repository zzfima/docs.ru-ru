---
title: Свойство Склстреамчарс. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395734"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="89d6c-102">Склстреамчарс. IsNull, свойство</span><span class="sxs-lookup"><span data-stu-id="89d6c-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="89d6c-103">При переопределении в производном классе получает значение, указывающее, является ли поток `null`.</span><span class="sxs-lookup"><span data-stu-id="89d6c-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="89d6c-104">Сборка, содержащая это свойство, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="89d6c-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="89d6c-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89d6c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="89d6c-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="89d6c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="89d6c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89d6c-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="89d6c-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="89d6c-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="89d6c-109">`true`, если поток `null`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="89d6c-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="89d6c-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="89d6c-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="89d6c-111">Свойство `SqlStreamChars.IsNull` является закрытым и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="89d6c-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="89d6c-112">Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="89d6c-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="89d6c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="89d6c-113">Requirements</span></span>

<span data-ttu-id="89d6c-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="89d6c-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="89d6c-115">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="89d6c-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="89d6c-116">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="89d6c-116">**.NET Framework versions:** Available since 2.0.</span></span>
