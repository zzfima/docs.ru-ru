---
title: typeof. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 3fa82a6faee345be77fc8ea3f5aa3342adecb0f5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244847"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="48fd9-102">typeof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="48fd9-102">typeof (C# Reference)</span></span>

<span data-ttu-id="48fd9-103">Позволяет получить объект <xref:System.Type?displayProperty=nameWithType> для типа.</span><span class="sxs-lookup"><span data-stu-id="48fd9-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="48fd9-104">Выражение `typeof` принимает следующую форму:</span><span class="sxs-lookup"><span data-stu-id="48fd9-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="48fd9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="48fd9-105">Remarks</span></span>

<span data-ttu-id="48fd9-106">Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="48fd9-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="48fd9-107">Оператор `typeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="48fd9-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="48fd9-108">Оператор `typeof` можно также применять к открытым универсальным типам.</span><span class="sxs-lookup"><span data-stu-id="48fd9-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="48fd9-109">Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации.</span><span class="sxs-lookup"><span data-stu-id="48fd9-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="48fd9-110">В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="48fd9-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="48fd9-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> возвращает `null`, если тип возвращаемого значения не является универсальным типом <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="48fd9-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="48fd9-112">Пример</span><span class="sxs-lookup"><span data-stu-id="48fd9-112">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="48fd9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="48fd9-113">Example</span></span>

<span data-ttu-id="48fd9-114">В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления.</span><span class="sxs-lookup"><span data-stu-id="48fd9-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="48fd9-115">Он зависит от требований к хранилищу для полученного числа.</span><span class="sxs-lookup"><span data-stu-id="48fd9-115">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="48fd9-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="48fd9-116">C# language specification</span></span>

<span data-ttu-id="48fd9-117">Дополнительные сведения см. в разделе [Оператор typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="48fd9-117">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="48fd9-118">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="48fd9-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="48fd9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="48fd9-119">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="48fd9-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="48fd9-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="48fd9-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="48fd9-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="48fd9-122">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="48fd9-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="48fd9-123">is</span><span class="sxs-lookup"><span data-stu-id="48fd9-123">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="48fd9-124">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="48fd9-124">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)