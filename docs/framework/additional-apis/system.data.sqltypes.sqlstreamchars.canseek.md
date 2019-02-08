---
title: Свойство SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: bde4764af9d0160997dc202f722a12393cfa59c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826854"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="585a0-102">Свойство SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="585a0-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="585a0-103">При переопределении в производном классе получает значение, указывающее, поддерживает ли текущий поток операции поиска.</span><span class="sxs-lookup"><span data-stu-id="585a0-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="585a0-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="585a0-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="585a0-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="585a0-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="585a0-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="585a0-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="585a0-107">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="585a0-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="585a0-108">`true` Если текущий поток поддерживает операции поиска; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="585a0-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="585a0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="585a0-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="585a0-110">`SqlStreamChars.CanSeek` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="585a0-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="585a0-111">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="585a0-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="585a0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="585a0-112">Requirements</span></span>

<span data-ttu-id="585a0-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="585a0-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="585a0-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="585a0-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="585a0-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="585a0-115">**.NET Framework versions:** Available since 2.0.</span></span>