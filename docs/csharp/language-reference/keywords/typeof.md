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
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422552"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="97e6e-102">typeof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="97e6e-102">typeof (C# Reference)</span></span>

<span data-ttu-id="97e6e-103">Позволяет получить объект <xref:System.Type?displayProperty=nameWithType> для типа.</span><span class="sxs-lookup"><span data-stu-id="97e6e-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="97e6e-104">Выражение `typeof` принимает следующую форму:</span><span class="sxs-lookup"><span data-stu-id="97e6e-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="97e6e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="97e6e-105">Remarks</span></span>

<span data-ttu-id="97e6e-106">Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="97e6e-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="97e6e-107">Оператор `typeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="97e6e-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="97e6e-108">Оператор `typeof` можно также применять к открытым универсальным типам.</span><span class="sxs-lookup"><span data-stu-id="97e6e-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="97e6e-109">Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации.</span><span class="sxs-lookup"><span data-stu-id="97e6e-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="97e6e-110">Например, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> имеет два аргумента типа, поэтому используйте одну запятую:</span><span class="sxs-lookup"><span data-stu-id="97e6e-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="97e6e-111">В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="97e6e-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="97e6e-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> возвращает `null`, если тип возвращаемого значения не является универсальным типом <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="97e6e-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="97e6e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="97e6e-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="97e6e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="97e6e-114">Example</span></span>

<span data-ttu-id="97e6e-115">В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления.</span><span class="sxs-lookup"><span data-stu-id="97e6e-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="97e6e-116">Он зависит от требований к хранилищу для полученного числа.</span><span class="sxs-lookup"><span data-stu-id="97e6e-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="97e6e-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="97e6e-117">C# language specification</span></span>

<span data-ttu-id="97e6e-118">Дополнительные сведения см. в разделе [Оператор typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="97e6e-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="97e6e-119">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="97e6e-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="97e6e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="97e6e-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="97e6e-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="97e6e-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="97e6e-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="97e6e-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="97e6e-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="97e6e-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="97e6e-124">is</span><span class="sxs-lookup"><span data-stu-id="97e6e-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
