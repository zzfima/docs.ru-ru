---
title: Свойство SqlStreamChars.Length (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3b4e5828a90de7d2f874010b79a9ddbcb8e12341
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827703"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="42659-102">Свойство SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="42659-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="42659-103">При переопределении в производном классе получает длину текущего потока.</span><span class="sxs-lookup"><span data-stu-id="42659-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="42659-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="42659-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="42659-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42659-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="42659-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="42659-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="42659-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42659-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="42659-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="42659-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="42659-109">Длина потока.</span><span class="sxs-lookup"><span data-stu-id="42659-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="42659-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="42659-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="42659-111">`SqlStreamChars.Length` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="42659-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="42659-112">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="42659-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="42659-113">Требования</span><span class="sxs-lookup"><span data-stu-id="42659-113">Requirements</span></span>

<span data-ttu-id="42659-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="42659-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="42659-115">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="42659-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="42659-116">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="42659-116">**.NET Framework versions:** Available since 2.0.</span></span>