---
title: Метод Склстреамчарс. Write (char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395579"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="18d9d-102">Метод Склстреамчарс. Write (char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="18d9d-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="18d9d-103">При переопределении в производном классе записывает последовательность символов в текущий поток и перемещает текущую позицию в этом потоке вперед на число записанных символов.</span><span class="sxs-lookup"><span data-stu-id="18d9d-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="18d9d-104">Сборка, содержащая этот метод, имеет дружественную связь с Склакцесс. dll.</span><span class="sxs-lookup"><span data-stu-id="18d9d-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="18d9d-105">Он предназначен для использования SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18d9d-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="18d9d-106">Для других баз данных используйте механизм размещения, предоставляемый этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="18d9d-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="18d9d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="18d9d-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="18d9d-108">Массив символов для записи.</span><span class="sxs-lookup"><span data-stu-id="18d9d-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="18d9d-109">Смещение относительно начала координат.</span><span class="sxs-lookup"><span data-stu-id="18d9d-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="18d9d-110">Число символов, записываемых в текущий поток.</span><span class="sxs-lookup"><span data-stu-id="18d9d-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="18d9d-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="18d9d-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="18d9d-112">Метод `SqlStreamChars.Write` является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="18d9d-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="18d9d-113">Корпорация Майкрософт не поддерживает использование этого метода для написания в рабочем приложении каких-либо обстоятельств.</span><span class="sxs-lookup"><span data-stu-id="18d9d-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="18d9d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="18d9d-114">Requirements</span></span>

<span data-ttu-id="18d9d-115">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="18d9d-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="18d9d-116">**Сборка:** System. Data (в System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="18d9d-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="18d9d-117">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="18d9d-117">**.NET Framework versions:** Available since 2.0.</span></span>
