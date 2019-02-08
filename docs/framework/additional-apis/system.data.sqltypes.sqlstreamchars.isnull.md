---
title: SqlStreamChars.IsNull Property (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7d2a2cf66ce2a375b1e5989b2fb6ddc9e3d94411
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825450"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="cb0f8-102">Свойство SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="cb0f8-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="cb0f8-103">При переопределении в производном классе получает значение, указывающее, является ли поток `null`.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="cb0f8-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="cb0f8-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="cb0f8-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb0f8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb0f8-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="cb0f8-108">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="cb0f8-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="cb0f8-109">`true` Если поток `null`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb0f8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb0f8-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="cb0f8-111">`SqlStreamChars.IsNull` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cb0f8-112">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb0f8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cb0f8-113">Requirements</span></span>

<span data-ttu-id="cb0f8-114">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="cb0f8-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="cb0f8-115">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="cb0f8-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="cb0f8-116">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="cb0f8-116">**.NET Framework versions:** Available since 2.0.</span></span>