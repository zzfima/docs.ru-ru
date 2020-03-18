---
title: Память и диапазоны
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: b61b1dbbedf4658fe113986fbb4a792a2f574534
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121991"
---
# <a name="memory--and-span-related-types"></a><span data-ttu-id="79c92-102">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="79c92-102">Memory- and span-related types</span></span>

<span data-ttu-id="79c92-103">Начиная с .NET Core 2.1, .NET включает ряд взаимосвязанных типов, представляющих непрерывную область строго типизированной произвольной памяти.</span><span class="sxs-lookup"><span data-stu-id="79c92-103">Starting with .NET Core 2.1, .NET includes a number of interrelated types that represent a contiguous, strongly-typed region of arbitrary memory.</span></span> <span data-ttu-id="79c92-104">К ним относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="79c92-104">These include:</span></span>

- <span data-ttu-id="79c92-105"><xref:System.Span%601?displayProperty=nameWithType> — тип, используемый для доступа к непрерывной области памяти.</span><span class="sxs-lookup"><span data-stu-id="79c92-105"><xref:System.Span%601?displayProperty=nameWithType>, a type that is used to access a contiguous region of memory.</span></span> <span data-ttu-id="79c92-106">В основе экземпляра <xref:System.Span%601> может быть массив типа `T`, <xref:System.String>, буфер, выделенный с помощью [stackalloc](../../csharp/language-reference/operators/stackalloc.md), или указатель на неуправляемую память.</span><span class="sxs-lookup"><span data-stu-id="79c92-106">A <xref:System.Span%601> instance can be backed by an array of type `T`, a <xref:System.String>, a buffer allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), or a pointer to unmanaged memory.</span></span> <span data-ttu-id="79c92-107">Так как выделение выполняется в стеке, существует ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="79c92-107">Because it has to be allocated on the stack, it has a number of restrictions.</span></span> <span data-ttu-id="79c92-108">Например, поле в классе не может иметь тип <xref:System.Span%601>, а диапазон нельзя использовать в асинхронных операциях.</span><span class="sxs-lookup"><span data-stu-id="79c92-108">For example, a field in a class cannot be of type <xref:System.Span%601>, nor can span be used in asynchronous operations.</span></span>

- <span data-ttu-id="79c92-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="79c92-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Span%601> structure.</span></span>

- <span data-ttu-id="79c92-110"><xref:System.Memory%601?displayProperty=nameWithType> — непрерывная область памяти, которая выделяется в управляемой куче, а не стеке.</span><span class="sxs-lookup"><span data-stu-id="79c92-110"><xref:System.Memory%601?displayProperty=nameWithType>, a contiguous region of memory that is allocated on the managed heap rather than the stack.</span></span> <span data-ttu-id="79c92-111">В основе экземпляра <xref:System.Memory%601> может быть массив объектов типа `T` или <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="79c92-111">A <xref:System.Memory%601> instance can be backed by an array of type `T` or a <xref:System.String>.</span></span> <span data-ttu-id="79c92-112">Так как он может храниться в управляемой куче, <xref:System.Memory%601> не имеет ограничений, применимых к <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="79c92-112">Because it can be stored on the managed heap, <xref:System.Memory%601> has none of the limitations of <xref:System.Span%601>.</span></span>

- <span data-ttu-id="79c92-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="79c92-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Memory%601> structure.</span></span>

- <span data-ttu-id="79c92-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType> — выделяет строго типизированные блоки памяти из пула памяти для владельца.</span><span class="sxs-lookup"><span data-stu-id="79c92-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, which allocates strongly-typed blocks of memory from a memory pool to an owner.</span></span> <span data-ttu-id="79c92-115">Экземпляры <xref:System.Buffers.IMemoryOwner%601> можно арендовать из пула путем вызова <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>, и освобождать в пул путем вызова <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79c92-115"><xref:System.Buffers.IMemoryOwner%601> instances can be rented from the pool by calling <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> and released back to the pool by calling <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="79c92-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> — представляет владельца блока памяти и управляет временем ее существования.</span><span class="sxs-lookup"><span data-stu-id="79c92-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, which represents the owner of a block of memory and controls its lifetime management.</span></span>

- <span data-ttu-id="79c92-117"><xref:System.Buffers.MemoryManager%601> — абстрактный базовый класс, используемый для замены реализации <xref:System.Memory%601>, чтобы включить для <xref:System.Memory%601> поддержку дополнительных типов, включая безопасные дескрипторы.</span><span class="sxs-lookup"><span data-stu-id="79c92-117"><xref:System.Buffers.MemoryManager%601>, an abstract base class that can be used to replace the implementation of <xref:System.Memory%601> so that <xref:System.Memory%601> can be backed by additional types, such as safe handles.</span></span> <span data-ttu-id="79c92-118"><xref:System.Buffers.MemoryManager%601> — используется только в сложных сценариях.</span><span class="sxs-lookup"><span data-stu-id="79c92-118"><xref:System.Buffers.MemoryManager%601> is intended for advanced scenarios.</span></span>

- <span data-ttu-id="79c92-119"><xref:System.ArraySegment%601> — программа-оболочка для определенного числа элементов массива, начиная с определенного индекса.</span><span class="sxs-lookup"><span data-stu-id="79c92-119"><xref:System.ArraySegment%601>, a wrapper for a particular number of array elements starting at a particular index.</span></span>

- <span data-ttu-id="79c92-120"><xref:System.MemoryExtensions?displayProperty=nameWithType> — коллекция методов расширения для преобразования строк, массивов и фрагментов массивов для блоков <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="79c92-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, a collection of extension methods for converting strings, arrays, and array segments to <xref:System.Memory%601> blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="79c92-121">Для более ранних платформ <xref:System.Span%601> и <xref:System.Memory%601> доступны в [пакете System.Memory NuGet](https://www.nuget.org/packages/System.Memory/).</span><span class="sxs-lookup"><span data-stu-id="79c92-121">For earlier frameworks, <xref:System.Span%601> and <xref:System.Memory%601> are available in the [System.Memory NuGet package](https://www.nuget.org/packages/System.Memory/).</span></span>

<span data-ttu-id="79c92-122">Дополнительные сведения см. в описании пространства имен <xref:System.Buffers?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79c92-122">For more information, see the <xref:System.Buffers?displayProperty=nameWithType> namespace.</span></span>

## <a name="working-with-memory-and-span"></a><span data-ttu-id="79c92-123">Использование памяти и диапазонов</span><span class="sxs-lookup"><span data-stu-id="79c92-123">Working with memory and span</span></span>

<span data-ttu-id="79c92-124">Так как типы, связанные с памятью и диапазонами, обычно используются для хранения данных в конвейере обработки, очень важно, чтобы разработчики следовали набору рекомендаций при использовании <xref:System.Span%601>, <xref:System.Memory%601> и связанных типов.</span><span class="sxs-lookup"><span data-stu-id="79c92-124">Because the memory- and span-related types are typically used to store data in a processing pipeline, it is important that developers follow a set of best practices when using <xref:System.Span%601>, <xref:System.Memory%601>, and related types.</span></span> <span data-ttu-id="79c92-125">Эти рекомендации описаны в руководствах по использованию структур [Memory\<T> и Span\<T>](memory-t-usage-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="79c92-125">These best practices are documented in [Memory\<T> and Span\<T> usage guidelines](memory-t-usage-guidelines.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79c92-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79c92-126">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
