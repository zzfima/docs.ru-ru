---
title: Руководство по программированию на C#. Доступ к элементу массива с использованием указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 4f5d82e0ccdffcb694e3030aabe58b8da687a5e1
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084801"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="652de-102">Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="652de-102">How to access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="652de-103">В небезопасном контексте для доступа к элементу в памяти можно использовать доступ к элементу указателя, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="652de-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="652de-104">Выражение в квадратных скобках должно допускать неявное преобразование в `int`, `uint`, `long` или `ulong`.</span><span class="sxs-lookup"><span data-stu-id="652de-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="652de-105">Операция `p[e]` эквивалентна `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="652de-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="652de-106">Как и в C или C++, при доступе к элементу указателя не выполняется проверка на ошибки выхода за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="652de-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="652de-107">Пример</span><span class="sxs-lookup"><span data-stu-id="652de-107">Example</span></span>

<span data-ttu-id="652de-108">В этом примере для массива символов `charPointer` выделено 123 расположения в памяти.</span><span class="sxs-lookup"><span data-stu-id="652de-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="652de-109">Этот массив использует два цикла [for](../../../csharp/language-reference/keywords/for.md) для отображения строчных и прописных букв.</span><span class="sxs-lookup"><span data-stu-id="652de-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="652de-110">Обратите внимание, что выражение `charPointer[i]` эквивалентно выражению `*(charPointer + i)` и с помощью любого из них можно получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="652de-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="652de-111">**Прописные буквы:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**буквы нижнего регистра:**
**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="652de-111">**Uppercase letters:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Lowercase letters:**
**abcdefghijklmnopqrstuvwxyz**</span></span>

## <a name="see-also"></a><span data-ttu-id="652de-112">См. также</span><span class="sxs-lookup"><span data-stu-id="652de-112">See also</span></span>

- [<span data-ttu-id="652de-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="652de-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="652de-114">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="652de-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="652de-115">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="652de-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="652de-116">Типы</span><span class="sxs-lookup"><span data-stu-id="652de-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="652de-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="652de-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="652de-118">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="652de-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="652de-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="652de-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
