---
title: Свойство SqlStreamChars.CanSeek (System.Data.SqlTypes)
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
ms.openlocfilehash: 52f88a3551e20c74d7a1144c3cd6859a023980db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675186"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="f17c9-102">Свойство SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="f17c9-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="f17c9-103">При переопределении в производном классе получает значение, указывающее, поддерживает ли текущий поток операции поиска.</span><span class="sxs-lookup"><span data-stu-id="f17c9-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="f17c9-104">Сборка, содержащая это свойство имеет с SQLAccess.dll связью.</span><span class="sxs-lookup"><span data-stu-id="f17c9-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f17c9-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f17c9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f17c9-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="f17c9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="f17c9-107">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="f17c9-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="f17c9-108">`true` Если текущий поток поддерживает операции поиска; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f17c9-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f17c9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f17c9-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f17c9-110">`SqlStreamChars.CanSeek` Свойство является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="f17c9-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f17c9-111">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="f17c9-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f17c9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f17c9-112">Requirements</span></span>

<span data-ttu-id="f17c9-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f17c9-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f17c9-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="f17c9-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f17c9-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f17c9-115">**.NET Framework versions:** Available since 2.0.</span></span>