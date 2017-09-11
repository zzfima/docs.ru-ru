---
title: "params (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="params-c-reference"></a><span data-ttu-id="69c07-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="69c07-102">params (C# Reference)</span></span>
<span data-ttu-id="69c07-103">С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="69c07-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="69c07-104">Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="69c07-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="69c07-105">Можно также не отправлять аргументы.</span><span class="sxs-lookup"><span data-stu-id="69c07-105">You also can send no arguments.</span></span> <span data-ttu-id="69c07-106">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="69c07-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="69c07-107">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="69c07-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69c07-108">Пример</span><span class="sxs-lookup"><span data-stu-id="69c07-108">Example</span></span>  
 <span data-ttu-id="69c07-109">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="69c07-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 <span data-ttu-id="69c07-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="69c07-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="69c07-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="69c07-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69c07-112">См. также</span><span class="sxs-lookup"><span data-stu-id="69c07-112">See Also</span></span>  
 <span data-ttu-id="69c07-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="69c07-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="69c07-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="69c07-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="69c07-115">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="69c07-115">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="69c07-116">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="69c07-116">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

