---
title: Метод SqlStreamChars.Flush (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 411bd0036de904dd485d9fb54fa5fd45e3b55dbb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634335"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="5eb00-102">Метод SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="5eb00-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="5eb00-103">При переопределении в производном классе очищает все буферы данного потока и вызывает запись данных буферов в базовое устройство.</span><span class="sxs-lookup"><span data-stu-id="5eb00-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="5eb00-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="5eb00-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5eb00-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5eb00-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5eb00-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="5eb00-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="5eb00-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5eb00-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="5eb00-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5eb00-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5eb00-109">`SqlStreamChars.Flush` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="5eb00-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5eb00-110">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="5eb00-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5eb00-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5eb00-111">Requirements</span></span>

<span data-ttu-id="5eb00-112">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5eb00-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5eb00-113">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="5eb00-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5eb00-114">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="5eb00-114">**.NET Framework versions:** Available since 2.0.</span></span>
