---
title: SqlStreamChars.Read(Char[], Int32, Int32) Method (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: da891ac1fcff0247a690770665ef1f3e487497b8
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825372"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="2e031-102">Метод SqlStreamChars.Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="2e031-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="2e031-103">При переопределении в производном классе, считывает следующий набор символов из входного потока.</span><span class="sxs-lookup"><span data-stu-id="2e031-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="2e031-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="2e031-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2e031-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2e031-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2e031-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="2e031-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="2e031-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e031-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="2e031-108">Массива символов для чтения.</span><span class="sxs-lookup"><span data-stu-id="2e031-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="2e031-109">Смещение относительно начала координат.</span><span class="sxs-lookup"><span data-stu-id="2e031-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="2e031-110">Число символов для чтения из текущего потока.</span><span class="sxs-lookup"><span data-stu-id="2e031-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="2e031-111">Returns</span><span class="sxs-lookup"><span data-stu-id="2e031-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="2e031-112">Общее количество символов, считанных в буфер.</span><span class="sxs-lookup"><span data-stu-id="2e031-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e031-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e031-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2e031-114">`SqlStreamChars.Read` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="2e031-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2e031-115">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="2e031-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e031-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2e031-116">Requirements</span></span>

<span data-ttu-id="2e031-117">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2e031-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2e031-118">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="2e031-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2e031-119">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="2e031-119">**.NET Framework versions:** Available since 2.0.</span></span>