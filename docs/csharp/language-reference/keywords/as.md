---
title: "as (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a><span data-ttu-id="9fcbb-102">as (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9fcbb-102">as (C# Reference)</span></span>
<span data-ttu-id="9fcbb-103">Оператор `as` можно использовать для выполнения определенных типов преобразований между совместимыми ссылочными типами или [типами, допускающими значение NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="9fcbb-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="9fcbb-104">Вот пример кода:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-104">The following code shows an example.</span></span>  
  
 <span data-ttu-id="9fcbb-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fcbb-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fcbb-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9fcbb-106">Remarks</span></span>  
 <span data-ttu-id="9fcbb-107">Оператор `as` аналогичен операции приведения.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-107">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="9fcbb-108">Однако, если преобразование невозможно, `as` возвращает `null`, а не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-108">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="9fcbb-109">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-109">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="9fcbb-110">Этот код является эквивалентом следующего выражения, за исключением того, что переменная `expression` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-110">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="9fcbb-111">Обратите внимание, что оператор `as` выполняет только преобразования ссылок, преобразования типов, допускающих значение NULL, и преобразования-упаковки.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-111">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="9fcbb-112">Оператор `as` не может выполнять другие преобразования, например пользовательские преобразования, которые следует выполнять с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-112">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcbb-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9fcbb-113">Example</span></span>  
 <span data-ttu-id="9fcbb-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fcbb-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9fcbb-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9fcbb-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fcbb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9fcbb-116">See Also</span></span>  
 <span data-ttu-id="9fcbb-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fcbb-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9fcbb-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fcbb-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9fcbb-119">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fcbb-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9fcbb-120">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="9fcbb-120">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="9fcbb-121">[Оператор ?:](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9fcbb-121">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 [<span data-ttu-id="9fcbb-122">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="9fcbb-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

