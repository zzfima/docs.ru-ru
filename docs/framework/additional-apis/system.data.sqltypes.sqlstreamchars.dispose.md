---
title: Метод SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: cc8df68a608000d89dd322b0d396504483bbf372
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675160"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="f7388-102">Метод SqlStreamChars.Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="f7388-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="f7388-103">При переопределении в производном классе, освобождает ресурсы, используемые в поток.</span><span class="sxs-lookup"><span data-stu-id="f7388-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="f7388-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="f7388-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f7388-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7388-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f7388-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="f7388-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="f7388-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7388-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="f7388-108">Значение `true` позволяет освободить как управляемые, так и неуправляемые ресурсы; значение `false` освобождает только неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f7388-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7388-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7388-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f7388-110">`SqlStreamChars.Dispose` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="f7388-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f7388-111">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="f7388-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7388-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f7388-112">Requirements</span></span>

<span data-ttu-id="f7388-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f7388-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f7388-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="f7388-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f7388-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f7388-115">**.NET Framework versions:** Available since 2.0.</span></span>