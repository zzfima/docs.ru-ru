---
title: as (Справочник по C#)
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: ce3163f7d957df96a5c0304adc0b3083d8e20104
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122731"
---
# <a name="as-c-reference"></a><span data-ttu-id="f4384-102">as (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f4384-102">as (C# Reference)</span></span>
<span data-ttu-id="f4384-103">Оператор `as` можно использовать для выполнения определенных типов преобразований между совместимыми ссылочными типами или [типами, допускающими значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4384-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="f4384-104">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="f4384-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="f4384-105">Как показано в примере, нужно сравнить результат выражения `as` со значением `null`, чтобы проверить, успешно ли выполнено преобразование.</span><span class="sxs-lookup"><span data-stu-id="f4384-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="f4384-106">Начиная с версии C# 7.0 можно использовать выражение [is](is.md) для проверки, успешно ли выполнено преобразование, и условного назначения переменной, если преобразование выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="f4384-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="f4384-107">Во многих случаях такое выражение будет короче, чем при использовании оператора `as`.</span><span class="sxs-lookup"><span data-stu-id="f4384-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="f4384-108">Дополнительные сведения см. в разделе [Шаблон типа](is.md#type) в статье об [операторе `is`](is.md).</span><span class="sxs-lookup"><span data-stu-id="f4384-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f4384-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4384-109">Remarks</span></span>  
 <span data-ttu-id="f4384-110">Оператор `as` аналогичен операции приведения.</span><span class="sxs-lookup"><span data-stu-id="f4384-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="f4384-111">Однако, если преобразование невозможно, `as` возвращает `null`, а не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="f4384-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="f4384-112">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f4384-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="f4384-113">Этот код является эквивалентом следующего выражения, за исключением того, что переменная `expression` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="f4384-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="f4384-114">Обратите внимание, что оператор `as` выполняет только преобразования ссылок, преобразования типов, допускающих значение NULL, и преобразования-упаковки.</span><span class="sxs-lookup"><span data-stu-id="f4384-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="f4384-115">Оператор `as` не может выполнять другие преобразования, например пользовательские преобразования, которые следует выполнять с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="f4384-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4384-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f4384-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="f4384-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f4384-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4384-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f4384-118">See Also</span></span>  
- [<span data-ttu-id="f4384-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f4384-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f4384-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f4384-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f4384-121">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f4384-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="f4384-122">is</span><span class="sxs-lookup"><span data-stu-id="f4384-122">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="f4384-123">Оператор ?:</span><span class="sxs-lookup"><span data-stu-id="f4384-123">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="f4384-124">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="f4384-124">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
