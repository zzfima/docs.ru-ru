---
title: Справочник по C#. Оператор as
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: b87e75bd4866a191e84465e44d53850e6e2e9723
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169927"
---
# <a name="as-c-reference"></a><span data-ttu-id="4c36b-102">as (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4c36b-102">as (C# Reference)</span></span>
<span data-ttu-id="4c36b-103">Оператор `as` можно использовать для выполнения определенных типов преобразований между совместимыми ссылочными типами или [типами, допускающими значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="4c36b-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="4c36b-104">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="4c36b-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="4c36b-105">Как показано в примере, нужно сравнить результат выражения `as` со значением `null`, чтобы проверить, успешно ли выполнено преобразование.</span><span class="sxs-lookup"><span data-stu-id="4c36b-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="4c36b-106">Начиная с версии C# 7.0 можно использовать выражение [is](is.md) для проверки, успешно ли выполнено преобразование, и условного назначения переменной, если преобразование выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="4c36b-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="4c36b-107">Во многих случаях такое выражение будет короче, чем при использовании оператора `as`.</span><span class="sxs-lookup"><span data-stu-id="4c36b-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="4c36b-108">Дополнительные сведения см. в разделе [Шаблон типа](is.md#type) в статье об [операторе `is`](is.md).</span><span class="sxs-lookup"><span data-stu-id="4c36b-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c36b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c36b-109">Remarks</span></span>  
 <span data-ttu-id="4c36b-110">Оператор `as` аналогичен операции приведения.</span><span class="sxs-lookup"><span data-stu-id="4c36b-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="4c36b-111">Однако, если преобразование невозможно, `as` возвращает `null`, а не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="4c36b-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="4c36b-112">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="4c36b-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="4c36b-113">Этот код является эквивалентом следующего выражения, за исключением того, что переменная `expression` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="4c36b-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="4c36b-114">Обратите внимание, что оператор `as` выполняет только преобразования ссылок, преобразования типов, допускающих значение NULL, и преобразования-упаковки.</span><span class="sxs-lookup"><span data-stu-id="4c36b-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="4c36b-115">Оператор `as` не может выполнять другие преобразования, например пользовательские преобразования, которые следует выполнять с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="4c36b-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c36b-116">Пример</span><span class="sxs-lookup"><span data-stu-id="4c36b-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="4c36b-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4c36b-117">C# Language Specification</span></span>  

<span data-ttu-id="4c36b-118">Дополнительные сведения см. в разделе [Оператор as](~/_csharplang/spec/expressions.md#the-as-operator) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4c36b-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="4c36b-119">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="4c36b-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="4c36b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4c36b-120">See also</span></span>

- [<span data-ttu-id="4c36b-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4c36b-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="4c36b-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4c36b-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4c36b-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="4c36b-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="4c36b-124">is</span><span class="sxs-lookup"><span data-stu-id="4c36b-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="4c36b-125">?: Оператор</span><span class="sxs-lookup"><span data-stu-id="4c36b-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)
- [<span data-ttu-id="4c36b-126">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="4c36b-126">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
