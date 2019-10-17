---
title: Метод Склстреамчарс. Read (char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395754"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="5b66d-102">Метод Склстреамчарс. Read (char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="5b66d-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="5b66d-103">При переопределении в производном классе считывает следующий набор символов из входного потока.</span><span class="sxs-lookup"><span data-stu-id="5b66d-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="5b66d-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="5b66d-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5b66d-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b66d-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5b66d-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="5b66d-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="5b66d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b66d-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="5b66d-108">Массив символов для чтения.</span><span class="sxs-lookup"><span data-stu-id="5b66d-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="5b66d-109">Смещение относительно начала координат.</span><span class="sxs-lookup"><span data-stu-id="5b66d-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="5b66d-110">Число символов, считываемых из текущего потока.</span><span class="sxs-lookup"><span data-stu-id="5b66d-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="5b66d-111">Returns</span><span class="sxs-lookup"><span data-stu-id="5b66d-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="5b66d-112">Общее количество символов, считанных в буфер.</span><span class="sxs-lookup"><span data-stu-id="5b66d-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b66d-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="5b66d-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5b66d-114">Метод `SqlStreamChars.Read` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="5b66d-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5b66d-115">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="5b66d-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b66d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="5b66d-116">Requirements</span></span>

<span data-ttu-id="5b66d-117">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5b66d-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5b66d-118">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="5b66d-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5b66d-119">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="5b66d-119">**.NET Framework versions:** Available since 2.0.</span></span>
