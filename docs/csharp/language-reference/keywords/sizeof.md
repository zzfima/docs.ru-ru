---
title: sizeof (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 37eb9345edc31a8d318540fd528f311059225de4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184209"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="4d0c1-102">sizeof (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="4d0c1-103">Позволяет получить размер в байтах для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="4d0c1-104">К неуправляемым типам относятся:</span><span class="sxs-lookup"><span data-stu-id="4d0c1-104">Unmanaged types include:</span></span>

- <span data-ttu-id="4d0c1-105">Простые типы, которые перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="4d0c1-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="4d0c1-106">Выражение</span><span class="sxs-lookup"><span data-stu-id="4d0c1-106">Expression</span></span>|<span data-ttu-id="4d0c1-107">Константа</span><span class="sxs-lookup"><span data-stu-id="4d0c1-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="4d0c1-108">1</span><span class="sxs-lookup"><span data-stu-id="4d0c1-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="4d0c1-109">1</span><span class="sxs-lookup"><span data-stu-id="4d0c1-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="4d0c1-110">2</span><span class="sxs-lookup"><span data-stu-id="4d0c1-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="4d0c1-111">2</span><span class="sxs-lookup"><span data-stu-id="4d0c1-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="4d0c1-112">4</span><span class="sxs-lookup"><span data-stu-id="4d0c1-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="4d0c1-113">4</span><span class="sxs-lookup"><span data-stu-id="4d0c1-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="4d0c1-114">8</span><span class="sxs-lookup"><span data-stu-id="4d0c1-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="4d0c1-115">8</span><span class="sxs-lookup"><span data-stu-id="4d0c1-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="4d0c1-116">2 (Юникод)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="4d0c1-117">4</span><span class="sxs-lookup"><span data-stu-id="4d0c1-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="4d0c1-118">8</span><span class="sxs-lookup"><span data-stu-id="4d0c1-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="4d0c1-119">16</span><span class="sxs-lookup"><span data-stu-id="4d0c1-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="4d0c1-120">1</span><span class="sxs-lookup"><span data-stu-id="4d0c1-120">1</span></span>|

- <span data-ttu-id="4d0c1-121">Типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-121">Enum types.</span></span>

- <span data-ttu-id="4d0c1-122">Типы указателей.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-122">Pointer types.</span></span>

- <span data-ttu-id="4d0c1-123">Определяемые пользователем структуры, которые не содержат полей экземпляров или автоматически реализуемых свойств, являющихся ссылочными или сконструированными типами.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="4d0c1-124">В приведенном ниже примере показано, как извлекать размер переменной типа `int`.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="4d0c1-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d0c1-125">Remarks</span></span>

<span data-ttu-id="4d0c1-126">Начиная с версии 2.0 языка C# применение `sizeof` к простым типам или типам перечисления больше не требует компиляции кода в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="4d0c1-127">Оператор `sizeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="4d0c1-128">Возвращаемые оператором `sizeof` значения принадлежат типу `int`.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="4d0c1-129">В предыдущей таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды простых типов.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="4d0c1-130">Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="4d0c1-131">Несмотря на то, что вы можете использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, возвращаемое им значение не всегда совпадает со значением, которое возвращает метод `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="4d0c1-132">Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="4d0c1-133">Пример</span><span class="sxs-lookup"><span data-stu-id="4d0c1-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="4d0c1-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4d0c1-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4d0c1-135">См. также</span><span class="sxs-lookup"><span data-stu-id="4d0c1-135">See also</span></span>

- [<span data-ttu-id="4d0c1-136">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4d0c1-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4d0c1-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4d0c1-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4d0c1-138">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="4d0c1-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4d0c1-139">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="4d0c1-139">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="4d0c1-140">enum</span><span class="sxs-lookup"><span data-stu-id="4d0c1-140">enum</span></span>](enum.md)
- [<span data-ttu-id="4d0c1-141">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="4d0c1-141">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="4d0c1-142">Структуры</span><span class="sxs-lookup"><span data-stu-id="4d0c1-142">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="4d0c1-143">Константы</span><span class="sxs-lookup"><span data-stu-id="4d0c1-143">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)