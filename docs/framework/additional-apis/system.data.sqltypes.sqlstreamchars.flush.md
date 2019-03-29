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
ms.openlocfilehash: 8cd24a5ca420552f283da61ecd4edcad02965403
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634197"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="0499c-102">Метод SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="0499c-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="0499c-103">При переопределении в производном классе очищает все буферы данного потока и вызывает запись данных буферов в базовое устройство.</span><span class="sxs-lookup"><span data-stu-id="0499c-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="0499c-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="0499c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0499c-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0499c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0499c-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="0499c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="0499c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0499c-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="0499c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0499c-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0499c-109">`SqlStreamChars.Flush` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="0499c-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0499c-110">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="0499c-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0499c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0499c-111">Requirements</span></span>

<span data-ttu-id="0499c-112">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0499c-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0499c-113">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="0499c-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0499c-114">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="0499c-114">**.NET Framework versions:** Available since 2.0.</span></span>