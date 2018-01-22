---
title: "Маршалинг строк"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4d53cd4072ab3f9ff52729f122c0a0ecab400df
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="marshaling-strings"></a><span data-ttu-id="9f4e4-102">Маршалинг строк</span><span class="sxs-lookup"><span data-stu-id="9f4e4-102">Marshaling Strings</span></span>
<span data-ttu-id="9f4e4-103">При вызове неуправляемого кода копируются строковые аргументы, и при необходимости выполняется преобразование этих аргументов из формата .NET Framework (Юникод) в неуправляемый формат (ANSI).</span><span class="sxs-lookup"><span data-stu-id="9f4e4-103">Platform invoke copies string parameters, converting them from the .NET Framework format (Unicode) to the unmanaged format (ANSI), if needed.</span></span> <span data-ttu-id="9f4e4-104">Так как управляемые строки являются неизменяемыми, то при вызове неуправляемого кода они не копируются обратно из неуправляемой памяти в управляемую память при возврате из функции.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-104">Because managed strings are immutable, platform invoke does not copy them back from unmanaged memory to managed memory when the function returns.</span></span>  
  
 <span data-ttu-id="9f4e4-105">В таблице ниже представлены варианты маршалинга строк, описано их использование и приведена ссылка на соответствующий пример кода .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-105">The following table lists marshaling options for strings, describes their usage, and provides a link to the corresponding .NET Framework sample.</span></span>  
  
|<span data-ttu-id="9f4e4-106">String</span><span class="sxs-lookup"><span data-stu-id="9f4e4-106">String</span></span>|<span data-ttu-id="9f4e4-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9f4e4-107">Description</span></span>|<span data-ttu-id="9f4e4-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9f4e4-108">Sample</span></span>|  
|------------|-----------------|------------|  
|<span data-ttu-id="9f4e4-109">По значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-109">By value.</span></span>|<span data-ttu-id="9f4e4-110">Передает строки в качестве параметров In.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-110">Passes strings as In parameters.</span></span>|[<span data-ttu-id="9f4e4-111">MsgBox</span><span class="sxs-lookup"><span data-stu-id="9f4e4-111">MsgBox</span></span>](../../../docs/framework/interop/msgbox-sample.md)|  
|<span data-ttu-id="9f4e4-112">Как результат.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-112">As result.</span></span>|<span data-ttu-id="9f4e4-113">Возвращает строки из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-113">Returns strings from unmanaged code.</span></span>|[<span data-ttu-id="9f4e4-114">Строки</span><span class="sxs-lookup"><span data-stu-id="9f4e4-114">Strings</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="9f4e4-115">По ссылке.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-115">By reference.</span></span>|<span data-ttu-id="9f4e4-116">Передает строки в качестве параметров In/Out с помощью <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-116">Passes strings as In/Out parameters using <xref:System.Text.StringBuilder>.</span></span>|[<span data-ttu-id="9f4e4-117">Buffers</span><span class="sxs-lookup"><span data-stu-id="9f4e4-117">Buffers</span></span>](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|<span data-ttu-id="9f4e4-118">В структуре по значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-118">In a structure by value.</span></span>|<span data-ttu-id="9f4e4-119">Передает строки в структуре, которая является параметром In.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-119">Passes strings in a structure that is an In parameter.</span></span>|[<span data-ttu-id="9f4e4-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="9f4e4-120">Structs</span></span>](http://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|<span data-ttu-id="9f4e4-121">В структуре по ссылке **(char\*)**.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-121">In a structure by reference **(char\*)**.</span></span>|<span data-ttu-id="9f4e4-122">Передает строки в структуре, которая является параметром In/Out.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-122">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="9f4e4-123">Неуправляемая функция ожидает указатель на символьный буфер, и размер буфера является членом структуры.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-123">The unmanaged function expects a pointer to a character buffer and the buffer size is a member of the structure.</span></span>|[<span data-ttu-id="9f4e4-124">Строки</span><span class="sxs-lookup"><span data-stu-id="9f4e4-124">Strings</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|<span data-ttu-id="9f4e4-125">В структуре по ссылке **(char[])**.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-125">In a structure by reference **(char[])**.</span></span>|<span data-ttu-id="9f4e4-126">Передает строки в структуре, которая является параметром In/Out.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-126">Passes strings in a structure that is an In/Out parameter.</span></span> <span data-ttu-id="9f4e4-127">Неуправляемая функция ожидает внедренный символьный буфер.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-127">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="9f4e4-128">OSInfo</span><span class="sxs-lookup"><span data-stu-id="9f4e4-128">OSInfo</span></span>](http://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="9f4e4-129">В классе по значению **(char\*)**.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-129">In a class by value **(char\*)**.</span></span>|<span data-ttu-id="9f4e4-130">Передает строки в классе (класс является параметром In/Out).</span><span class="sxs-lookup"><span data-stu-id="9f4e4-130">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="9f4e4-131">Неуправляемая функция ожидает указатель на символьный буфер.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-131">The unmanaged function expects a pointer to a character buffer.</span></span>|[<span data-ttu-id="9f4e4-132">OpenFileDlg</span><span class="sxs-lookup"><span data-stu-id="9f4e4-132">OpenFileDlg</span></span>](http://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|<span data-ttu-id="9f4e4-133">В классе по значению **(char[])**.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-133">In a class by value **(char[])**.</span></span>|<span data-ttu-id="9f4e4-134">Передает строки в классе (класс является параметром In/Out).</span><span class="sxs-lookup"><span data-stu-id="9f4e4-134">Passes strings in a class (a class is an In/Out parameter).</span></span> <span data-ttu-id="9f4e4-135">Неуправляемая функция ожидает внедренный символьный буфер.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-135">The unmanaged function expects an embedded character buffer.</span></span>|[<span data-ttu-id="9f4e4-136">OSInfo</span><span class="sxs-lookup"><span data-stu-id="9f4e4-136">OSInfo</span></span>](http://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455)|  
|<span data-ttu-id="9f4e4-137">Как массив строк по значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-137">As an array of strings by value.</span></span>|<span data-ttu-id="9f4e4-138">Создает массив строк, который передается по значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-138">Creates an array of strings that is passed by value.</span></span>|[<span data-ttu-id="9f4e4-139">Массивы</span><span class="sxs-lookup"><span data-stu-id="9f4e4-139">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|<span data-ttu-id="9f4e4-140">Как массив структур, содержащих строки по значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-140">As an array of structures that contain strings by value.</span></span>|<span data-ttu-id="9f4e4-141">Создает массив структур, содержащих строки. Массив передается по значению.</span><span class="sxs-lookup"><span data-stu-id="9f4e4-141">Creates an array of structures that contain strings and the array is passed by value.</span></span>|[<span data-ttu-id="9f4e4-142">Массивы</span><span class="sxs-lookup"><span data-stu-id="9f4e4-142">Arrays</span></span>](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9f4e4-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9f4e4-143">See Also</span></span>  
 [<span data-ttu-id="9f4e4-144">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="9f4e4-144">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 [<span data-ttu-id="9f4e4-145">Типы данных вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="9f4e4-145">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="9f4e4-146">Маршалинг классов, структур и объединений</span><span class="sxs-lookup"><span data-stu-id="9f4e4-146">Marshaling Classes, Structures, and Unions</span></span>](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)  
 [<span data-ttu-id="9f4e4-147">Маршалинг массивов типов</span><span class="sxs-lookup"><span data-stu-id="9f4e4-147">Marshaling Arrays of Types</span></span>](http://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)  
 [<span data-ttu-id="9f4e4-148">Различные примеры маршалинга</span><span class="sxs-lookup"><span data-stu-id="9f4e4-148">Miscellaneous Marshaling Samples</span></span>](http://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70)
