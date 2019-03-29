---
title: Метод SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1283fea83cf77bbc898d460feedc72b898a65fb7
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633950"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="1364a-102">Метод SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="1364a-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="1364a-103">При переопределении в производном классе, освобождает ресурсы, используемые в поток.</span><span class="sxs-lookup"><span data-stu-id="1364a-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="1364a-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="1364a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="1364a-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1364a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="1364a-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="1364a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="1364a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1364a-107">Parameters</span></span>

`value`\
<span data-ttu-id="1364a-108">Нужная длина текущего потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="1364a-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1364a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1364a-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="1364a-110">`SqlStreamChars.SetLength` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="1364a-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1364a-111">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="1364a-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="1364a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1364a-112">Requirements</span></span>

<span data-ttu-id="1364a-113">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="1364a-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="1364a-114">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="1364a-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="1364a-115">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="1364a-115">**.NET Framework versions:** Available since 2.0.</span></span>