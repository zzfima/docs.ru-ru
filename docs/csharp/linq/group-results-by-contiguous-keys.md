---
title: Группирование результатов по смежным ключам (LINQ в C#)
description: Как группировать результаты по смежным ключам с помощью LINQ в C#.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44209346"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="06614-103">Группирование результатов по смежным ключам</span><span class="sxs-lookup"><span data-stu-id="06614-103">Group results by contiguous keys</span></span>

<span data-ttu-id="06614-104">В приведенном ниже примере показано, как сгруппировать элементы в блоки, представляющие последовательности смежных ключей.</span><span class="sxs-lookup"><span data-stu-id="06614-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="06614-105">Например, предположим, что имеется следующая последовательность пар "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="06614-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="06614-106">Ключ</span><span class="sxs-lookup"><span data-stu-id="06614-106">Key</span></span>|<span data-ttu-id="06614-107">Значение</span><span class="sxs-lookup"><span data-stu-id="06614-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="06614-108">А</span><span class="sxs-lookup"><span data-stu-id="06614-108">A</span></span>|<span data-ttu-id="06614-109">Мы</span><span class="sxs-lookup"><span data-stu-id="06614-109">We</span></span>|
|<span data-ttu-id="06614-110">А</span><span class="sxs-lookup"><span data-stu-id="06614-110">A</span></span>|<span data-ttu-id="06614-111">думаем,</span><span class="sxs-lookup"><span data-stu-id="06614-111">think</span></span>|
|<span data-ttu-id="06614-112">А</span><span class="sxs-lookup"><span data-stu-id="06614-112">A</span></span>|<span data-ttu-id="06614-113">что</span><span class="sxs-lookup"><span data-stu-id="06614-113">that</span></span>|
|<span data-ttu-id="06614-114">С</span><span class="sxs-lookup"><span data-stu-id="06614-114">B</span></span>|<span data-ttu-id="06614-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="06614-115">Linq</span></span>|
|<span data-ttu-id="06614-116">В</span><span class="sxs-lookup"><span data-stu-id="06614-116">C</span></span>|<span data-ttu-id="06614-117">является</span><span class="sxs-lookup"><span data-stu-id="06614-117">is</span></span>|
|<span data-ttu-id="06614-118">А</span><span class="sxs-lookup"><span data-stu-id="06614-118">A</span></span>|<span data-ttu-id="06614-119">действительно</span><span class="sxs-lookup"><span data-stu-id="06614-119">really</span></span>|
|<span data-ttu-id="06614-120">С</span><span class="sxs-lookup"><span data-stu-id="06614-120">B</span></span>|<span data-ttu-id="06614-121">известным</span><span class="sxs-lookup"><span data-stu-id="06614-121">cool</span></span>|
|<span data-ttu-id="06614-122">С</span><span class="sxs-lookup"><span data-stu-id="06614-122">B</span></span>|<span data-ttu-id="06614-123">!</span><span class="sxs-lookup"><span data-stu-id="06614-123">!</span></span>|

<span data-ttu-id="06614-124">Следующие группы будут созданы в таком порядке:</span><span class="sxs-lookup"><span data-stu-id="06614-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="06614-125">Мы думаем, что</span><span class="sxs-lookup"><span data-stu-id="06614-125">We, think, that</span></span>

2. <span data-ttu-id="06614-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="06614-126">Linq</span></span>

3. <span data-ttu-id="06614-127">является</span><span class="sxs-lookup"><span data-stu-id="06614-127">is</span></span>

4. <span data-ttu-id="06614-128">действительно</span><span class="sxs-lookup"><span data-stu-id="06614-128">really</span></span>

5. <span data-ttu-id="06614-129">известным, !</span><span class="sxs-lookup"><span data-stu-id="06614-129">cool, !</span></span>

<span data-ttu-id="06614-130">Решение реализуется как метод расширения, который является потокобезопасным и возвращает результаты потоковым образом.</span><span class="sxs-lookup"><span data-stu-id="06614-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="06614-131">Иными словами, он создает группы по мере прохода по исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="06614-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="06614-132">В отличие от операторов `group` и `orderby`, он может начать возвращать группы вызывающему объекту до того, как будет прочитана вся последовательность.</span><span class="sxs-lookup"><span data-stu-id="06614-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="06614-133">Потокобезопасность обеспечивается созданием копии каждой группы или блока по мере итерации исходной последовательности, как указывается в комментариях исходного кода.</span><span class="sxs-lookup"><span data-stu-id="06614-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="06614-134">Если исходная последовательность имеет большой набор смежных элементов, среда CLR может создать исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="06614-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="06614-135">Пример</span><span class="sxs-lookup"><span data-stu-id="06614-135">Example</span></span>

<span data-ttu-id="06614-136">В приведенном ниже примере показаны метод расширения и использующий его клиентский код:</span><span class="sxs-lookup"><span data-stu-id="06614-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="06614-137">Чтобы использовать метод расширения в своем проекте, скопируйте статический класс `MyExtensions` в новый или существующий файл исходного кода и, если необходимо, добавьте директиву `using` для пространства имен, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="06614-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="06614-138">См. также</span><span class="sxs-lookup"><span data-stu-id="06614-138">See also</span></span>

- [<span data-ttu-id="06614-139">LINQ</span><span class="sxs-lookup"><span data-stu-id="06614-139">Language Integrated Query (LINQ)</span></span>](index.md)
