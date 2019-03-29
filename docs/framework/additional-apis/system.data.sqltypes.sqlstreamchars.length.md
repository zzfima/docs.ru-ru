---
title: Свойство SqlStreamChars.Length (System.Data.SqlTypes)
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
ms.openlocfilehash: c2ef66fa493512e1fa062e22858ea251ced39453
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634145"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="42785-102">Свойство SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="42785-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="42785-103">При переопределении в производном классе получает длину текущего потока.</span><span class="sxs-lookup"><span data-stu-id="42785-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="42785-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="42785-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="42785-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42785-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="42785-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="42785-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="42785-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42785-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="42785-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="42785-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="42785-109">Длина потока.</span><span class="sxs-lookup"><span data-stu-id="42785-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="42785-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="42785-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="42785-111">`SqlStreamChars.Length` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="42785-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="42785-112">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="42785-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="42785-113">Требования</span><span class="sxs-lookup"><span data-stu-id="42785-113">Requirements</span></span>

<span data-ttu-id="42785-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="42785-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="42785-115">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="42785-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="42785-116">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="42785-116">**.NET Framework versions:** Available since 2.0.</span></span>