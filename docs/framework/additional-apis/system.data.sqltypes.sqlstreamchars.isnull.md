---
title: SqlStreamChars.IsNull Property (System.Data.SqlTypes)
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
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675225"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="69367-102">Свойство SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="69367-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="69367-103">При переопределении в производном классе получает значение, указывающее, является ли поток `null`.</span><span class="sxs-lookup"><span data-stu-id="69367-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="69367-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="69367-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="69367-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69367-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="69367-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="69367-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="69367-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69367-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="69367-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="69367-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="69367-109">`true` Если поток `null`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="69367-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69367-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="69367-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="69367-111">`SqlStreamChars.IsNull` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="69367-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="69367-112">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="69367-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="69367-113">Требования</span><span class="sxs-lookup"><span data-stu-id="69367-113">Requirements</span></span>

<span data-ttu-id="69367-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="69367-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="69367-115">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="69367-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="69367-116">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="69367-116">**.NET Framework versions:** Available since 2.0.</span></span>