---
title: Руководство по программированию на C#. Доступ к элементу массива с использованием указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 7b2991776ca032aa53111187a061835725cfe223
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965609"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="3e324-102">Руководство по программированию на C#. Доступ к элементу массива с использованием указателя</span><span class="sxs-lookup"><span data-stu-id="3e324-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="3e324-103">В небезопасном контексте для доступа к элементу в памяти можно использовать доступ к элементу указателя, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3e324-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="3e324-104">Выражение в квадратных скобках должно допускать неявное преобразование в `int`, `uint`, `long` или `ulong`.</span><span class="sxs-lookup"><span data-stu-id="3e324-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="3e324-105">Операция `p[e]` эквивалентна `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="3e324-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="3e324-106">Как и в C или C++, при доступе к элементу указателя не выполняется проверка на ошибки выхода за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="3e324-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="3e324-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3e324-107">Example</span></span>

<span data-ttu-id="3e324-108">В этом примере для массива символов `charPointer` выделено 123 расположения в памяти.</span><span class="sxs-lookup"><span data-stu-id="3e324-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="3e324-109">Этот массив использует два цикла [for](../../../csharp/language-reference/keywords/for.md) для отображения строчных и прописных букв.</span><span class="sxs-lookup"><span data-stu-id="3e324-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="3e324-110">Обратите внимание, что выражение `charPointer[i]` эквивалентно выражению `*(charPointer + i)` и с помощью любого из них можно получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="3e324-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

 [!code-csharp[csProgGuidePointers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#11)]

 [!code-csharp[csProgGuidePointers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#12)]

<span data-ttu-id="3e324-111">**Прописные буквы:**</span><span class="sxs-lookup"><span data-stu-id="3e324-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="3e324-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="3e324-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="3e324-113">**Строчные буквы:**</span><span class="sxs-lookup"><span data-stu-id="3e324-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="3e324-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="3e324-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="3e324-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3e324-115">See also</span></span>

- [<span data-ttu-id="3e324-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3e324-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3e324-117">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="3e324-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="3e324-118">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="3e324-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="3e324-119">Типы</span><span class="sxs-lookup"><span data-stu-id="3e324-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="3e324-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="3e324-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="3e324-121">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="3e324-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="3e324-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3e324-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
