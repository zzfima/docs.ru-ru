---
title: Группирование результатов по смежным ключам
description: Сведения о группировании результатов по смежным ключам.
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281441"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="99882-103">Группирование результатов по смежным ключам</span><span class="sxs-lookup"><span data-stu-id="99882-103">Group results by contiguous keys</span></span>

<span data-ttu-id="99882-104">В приведенном ниже примере показано, как сгруппировать элементы в блоки, представляющие последовательности смежных ключей.</span><span class="sxs-lookup"><span data-stu-id="99882-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="99882-105">Например, предположим, что имеется следующая последовательность пар "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="99882-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="99882-106">Ключ</span><span class="sxs-lookup"><span data-stu-id="99882-106">Key</span></span>|<span data-ttu-id="99882-107">Значение</span><span class="sxs-lookup"><span data-stu-id="99882-107">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="99882-108">А</span><span class="sxs-lookup"><span data-stu-id="99882-108">A</span></span>|<span data-ttu-id="99882-109">Мы</span><span class="sxs-lookup"><span data-stu-id="99882-109">We</span></span>|  
|<span data-ttu-id="99882-110">А</span><span class="sxs-lookup"><span data-stu-id="99882-110">A</span></span>|<span data-ttu-id="99882-111">думаем,</span><span class="sxs-lookup"><span data-stu-id="99882-111">think</span></span>|  
|<span data-ttu-id="99882-112">А</span><span class="sxs-lookup"><span data-stu-id="99882-112">A</span></span>|<span data-ttu-id="99882-113">что</span><span class="sxs-lookup"><span data-stu-id="99882-113">that</span></span>|  
|<span data-ttu-id="99882-114">С</span><span class="sxs-lookup"><span data-stu-id="99882-114">B</span></span>|<span data-ttu-id="99882-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="99882-115">Linq</span></span>|  
|<span data-ttu-id="99882-116">В</span><span class="sxs-lookup"><span data-stu-id="99882-116">C</span></span>|<span data-ttu-id="99882-117">является</span><span class="sxs-lookup"><span data-stu-id="99882-117">is</span></span>|  
|<span data-ttu-id="99882-118">А</span><span class="sxs-lookup"><span data-stu-id="99882-118">A</span></span>|<span data-ttu-id="99882-119">действительно</span><span class="sxs-lookup"><span data-stu-id="99882-119">really</span></span>|  
|<span data-ttu-id="99882-120">С</span><span class="sxs-lookup"><span data-stu-id="99882-120">B</span></span>|<span data-ttu-id="99882-121">известным</span><span class="sxs-lookup"><span data-stu-id="99882-121">cool</span></span>|  
|<span data-ttu-id="99882-122">С</span><span class="sxs-lookup"><span data-stu-id="99882-122">B</span></span>|<span data-ttu-id="99882-123">!</span><span class="sxs-lookup"><span data-stu-id="99882-123">!</span></span>|  
  
 <span data-ttu-id="99882-124">Следующие группы будут созданы в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="99882-124">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="99882-125">Мы думаем, что</span><span class="sxs-lookup"><span data-stu-id="99882-125">We, think, that</span></span>  
  
2.  <span data-ttu-id="99882-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="99882-126">Linq</span></span>  
  
3.  <span data-ttu-id="99882-127">является</span><span class="sxs-lookup"><span data-stu-id="99882-127">is</span></span>  
  
4.  <span data-ttu-id="99882-128">действительно</span><span class="sxs-lookup"><span data-stu-id="99882-128">really</span></span>  
  
5.  <span data-ttu-id="99882-129">известным, !</span><span class="sxs-lookup"><span data-stu-id="99882-129">cool, !</span></span>  
  
 <span data-ttu-id="99882-130">Решение реализуется как метод расширения, который является потокобезопасным и возвращает результаты потоковым образом.</span><span class="sxs-lookup"><span data-stu-id="99882-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="99882-131">Иными словами, он создает группы по мере прохода по исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="99882-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="99882-132">В отличие от операторов `group` и `orderby`, он может начать возвращать группы вызывающему объекту до того, как будет прочитана вся последовательность.</span><span class="sxs-lookup"><span data-stu-id="99882-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="99882-133">Потокобезопасность обеспечивается созданием копии каждой группы или блока по мере итерации исходной последовательности, как указывается в комментариях исходного кода.</span><span class="sxs-lookup"><span data-stu-id="99882-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="99882-134">Если исходная последовательность имеет большой набор смежных элементов, среда CLR может создать исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="99882-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99882-135">Пример</span><span class="sxs-lookup"><span data-stu-id="99882-135">Example</span></span>  
 <span data-ttu-id="99882-136">В приведенном ниже примере показаны метод расширения и использующий его клиентский код.</span><span class="sxs-lookup"><span data-stu-id="99882-136">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="99882-137">Чтобы использовать метод расширения в своем проекте, скопируйте статический класс `MyExtensions` в новый или существующий файл исходного кода и, если необходимо, добавьте директиву `using` для пространства имен, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="99882-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99882-138">См. также</span><span class="sxs-lookup"><span data-stu-id="99882-138">See also</span></span>  
 [<span data-ttu-id="99882-139">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="99882-139">LINQ Query Expressions</span></span>](index.md)  
 
