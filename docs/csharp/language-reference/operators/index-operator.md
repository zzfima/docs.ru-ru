---
title: Справочник по C#. Оператор []
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835594"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="41b9d-102">Оператор [].Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="41b9d-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="41b9d-103">Квадратные скобки, `[]`, обычно используются для доступа к элементам массива, индексатора или указателя.</span><span class="sxs-lookup"><span data-stu-id="41b9d-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="41b9d-104">Дополнительные сведения см. в [практическом руководстве по доступу к элементу массива с использованием указателя](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="41b9d-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="41b9d-105">Кроме того, с помощью квадратных скобок можно указывать [атрибуты](../../programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b9d-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="41b9d-106">Доступ к массиву</span><span class="sxs-lookup"><span data-stu-id="41b9d-106">Array access</span></span>

<span data-ttu-id="41b9d-107">В приведенном ниже примере показано, как получить доступ к элементам массива.</span><span class="sxs-lookup"><span data-stu-id="41b9d-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="41b9d-108">Если индекс массива выходит за границы соответствующего измерения массива, возникает исключение <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="41b9d-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="41b9d-109">Как показано в предыдущем примере, квадратные скобки также используются в объявлении типа массива и для создания экземпляров массива.</span><span class="sxs-lookup"><span data-stu-id="41b9d-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="41b9d-110">Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b9d-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="41b9d-111">Доступ к индексатору</span><span class="sxs-lookup"><span data-stu-id="41b9d-111">Indexer access</span></span>

<span data-ttu-id="41b9d-112">В приведенном ниже примере используется тип .NET <xref:System.Collections.Generic.Dictionary%602> для демонстрации доступа к индексатору.</span><span class="sxs-lookup"><span data-stu-id="41b9d-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="41b9d-113">Индексаторы позволяют индексировать экземпляры определяемого пользователем типа аналогично индексации массива.</span><span class="sxs-lookup"><span data-stu-id="41b9d-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="41b9d-114">В отличие от индексов массива, которые должны быть целым числом, аргументы индексатора могут быть объявлены любым типом.</span><span class="sxs-lookup"><span data-stu-id="41b9d-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="41b9d-115">Дополнительные сведения см. в [руководстве по работе с индексаторами](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b9d-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="41b9d-116">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="41b9d-116">Operator overloadability</span></span>

<span data-ttu-id="41b9d-117">Доступ к элементам `[]` не считается перегружаемым оператором.</span><span class="sxs-lookup"><span data-stu-id="41b9d-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="41b9d-118">Используйте [индексаторы](../../programming-guide/indexers/index.md) для поддержки индексирования с помощью определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="41b9d-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="41b9d-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="41b9d-119">C# language specification</span></span>

<span data-ttu-id="41b9d-120">Дополнительные сведения см. в разделах [Доступ к элементам](~/_csharplang/spec/expressions.md#element-access) и [Доступ к элементу указателя](~/_csharplang/spec/unsafe-code.md#pointer-element-access) [спецификации C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b9d-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41b9d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="41b9d-121">See also</span></span>

- [<span data-ttu-id="41b9d-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="41b9d-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41b9d-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="41b9d-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="41b9d-124">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="41b9d-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="41b9d-125">Массивы</span><span class="sxs-lookup"><span data-stu-id="41b9d-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="41b9d-126">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="41b9d-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="41b9d-127">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="41b9d-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="41b9d-128">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41b9d-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="41b9d-129">[Операторы ?. и ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="41b9d-129">[?. and ?[] operators](null-conditional-operators.md)</span></span>