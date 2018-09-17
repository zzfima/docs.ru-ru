---
title: as (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: aee80b3262ccd9432d7c311dddec47185b66d05f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45648399"
---
# <a name="as-c-reference"></a><span data-ttu-id="3156f-102">as (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3156f-102">as (C# Reference)</span></span>
<span data-ttu-id="3156f-103">Оператор `as` можно использовать для выполнения определенных типов преобразований между совместимыми ссылочными типами или [типами, допускающими значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="3156f-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="3156f-104">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="3156f-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]
  
## <a name="remarks"></a><span data-ttu-id="3156f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3156f-105">Remarks</span></span>  
 <span data-ttu-id="3156f-106">Оператор `as` аналогичен операции приведения.</span><span class="sxs-lookup"><span data-stu-id="3156f-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="3156f-107">Однако, если преобразование невозможно, `as` возвращает `null`, а не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="3156f-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="3156f-108">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="3156f-108">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="3156f-109">Этот код является эквивалентом следующего выражения, за исключением того, что переменная `expression` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="3156f-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="3156f-110">Обратите внимание, что оператор `as` выполняет только преобразования ссылок, преобразования типов, допускающих значение NULL, и преобразования-упаковки.</span><span class="sxs-lookup"><span data-stu-id="3156f-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="3156f-111">Оператор `as` не может выполнять другие преобразования, например пользовательские преобразования, которые следует выполнять с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="3156f-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3156f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="3156f-112">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="3156f-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3156f-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3156f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3156f-114">See Also</span></span>  
- [<span data-ttu-id="3156f-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3156f-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3156f-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3156f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3156f-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="3156f-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3156f-118">is</span><span class="sxs-lookup"><span data-stu-id="3156f-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="3156f-119">Оператор ?:</span><span class="sxs-lookup"><span data-stu-id="3156f-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="3156f-120">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="3156f-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
