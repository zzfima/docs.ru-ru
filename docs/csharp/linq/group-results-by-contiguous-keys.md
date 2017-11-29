---
title: "Группирование результатов по смежным ключам"
description: "Сведения о группировании результатов по смежным ключам."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: cdd06a6fad037291bbc5aa011b47bb668fa2f062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="bf51a-104">Группирование результатов по смежным ключам</span><span class="sxs-lookup"><span data-stu-id="bf51a-104">Group results by contiguous keys</span></span>

<span data-ttu-id="bf51a-105">В приведенном ниже примере показано, как сгруппировать элементы в блоки, представляющие последовательности смежных ключей.</span><span class="sxs-lookup"><span data-stu-id="bf51a-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="bf51a-106">Например, предположим, что имеется следующая последовательность пар "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="bf51a-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="bf51a-107">Ключ</span><span class="sxs-lookup"><span data-stu-id="bf51a-107">Key</span></span>|<span data-ttu-id="bf51a-108">Значение</span><span class="sxs-lookup"><span data-stu-id="bf51a-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="bf51a-109">А</span><span class="sxs-lookup"><span data-stu-id="bf51a-109">A</span></span>|<span data-ttu-id="bf51a-110">Мы</span><span class="sxs-lookup"><span data-stu-id="bf51a-110">We</span></span>|  
|<span data-ttu-id="bf51a-111">А</span><span class="sxs-lookup"><span data-stu-id="bf51a-111">A</span></span>|<span data-ttu-id="bf51a-112">думаем,</span><span class="sxs-lookup"><span data-stu-id="bf51a-112">think</span></span>|  
|<span data-ttu-id="bf51a-113">А</span><span class="sxs-lookup"><span data-stu-id="bf51a-113">A</span></span>|<span data-ttu-id="bf51a-114">что</span><span class="sxs-lookup"><span data-stu-id="bf51a-114">that</span></span>|  
|<span data-ttu-id="bf51a-115">С</span><span class="sxs-lookup"><span data-stu-id="bf51a-115">B</span></span>|<span data-ttu-id="bf51a-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="bf51a-116">Linq</span></span>|  
|<span data-ttu-id="bf51a-117">C</span><span class="sxs-lookup"><span data-stu-id="bf51a-117">C</span></span>|<span data-ttu-id="bf51a-118">является</span><span class="sxs-lookup"><span data-stu-id="bf51a-118">is</span></span>|  
|<span data-ttu-id="bf51a-119">А</span><span class="sxs-lookup"><span data-stu-id="bf51a-119">A</span></span>|<span data-ttu-id="bf51a-120">действительно</span><span class="sxs-lookup"><span data-stu-id="bf51a-120">really</span></span>|  
|<span data-ttu-id="bf51a-121">С</span><span class="sxs-lookup"><span data-stu-id="bf51a-121">B</span></span>|<span data-ttu-id="bf51a-122">известным</span><span class="sxs-lookup"><span data-stu-id="bf51a-122">cool</span></span>|  
|<span data-ttu-id="bf51a-123">С</span><span class="sxs-lookup"><span data-stu-id="bf51a-123">B</span></span>|<span data-ttu-id="bf51a-124">!</span><span class="sxs-lookup"><span data-stu-id="bf51a-124">!</span></span>|  
  
 <span data-ttu-id="bf51a-125">Следующие группы будут созданы в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="bf51a-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="bf51a-126">Мы думаем, что</span><span class="sxs-lookup"><span data-stu-id="bf51a-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="bf51a-127">LINQ</span><span class="sxs-lookup"><span data-stu-id="bf51a-127">Linq</span></span>  
  
3.  <span data-ttu-id="bf51a-128">является</span><span class="sxs-lookup"><span data-stu-id="bf51a-128">is</span></span>  
  
4.  <span data-ttu-id="bf51a-129">действительно</span><span class="sxs-lookup"><span data-stu-id="bf51a-129">really</span></span>  
  
5.  <span data-ttu-id="bf51a-130">известным, !</span><span class="sxs-lookup"><span data-stu-id="bf51a-130">cool, !</span></span>  
  
 <span data-ttu-id="bf51a-131">Решение реализуется как метод расширения, который является потокобезопасным и возвращает результаты потоковым образом.</span><span class="sxs-lookup"><span data-stu-id="bf51a-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="bf51a-132">Иными словами, он создает группы по мере прохода по исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="bf51a-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="bf51a-133">В отличие от операторов `group` и `orderby`, он может начать возвращать группы вызывающему объекту до того, как будет прочитана вся последовательность.</span><span class="sxs-lookup"><span data-stu-id="bf51a-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="bf51a-134">Потокобезопасность обеспечивается созданием копии каждой группы или блока по мере итерации исходной последовательности, как указывается в комментариях исходного кода.</span><span class="sxs-lookup"><span data-stu-id="bf51a-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="bf51a-135">Если исходная последовательность имеет большой набор смежных элементов, среда CLR может создать исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="bf51a-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf51a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="bf51a-136">Example</span></span>  
 <span data-ttu-id="bf51a-137">В приведенном ниже примере показаны метод расширения и использующий его клиентский код.</span><span class="sxs-lookup"><span data-stu-id="bf51a-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="bf51a-138">Чтобы использовать метод расширения в своем проекте, скопируйте статический класс `MyExtensions` в новый или существующий файл исходного кода и, если необходимо, добавьте директиву `using` для пространства имен, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="bf51a-138">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf51a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="bf51a-139">See also</span></span>  
 [<span data-ttu-id="bf51a-140">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="bf51a-140">LINQ Query Expressions</span></span>](index.md)  
 
