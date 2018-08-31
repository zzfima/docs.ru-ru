---
title: params (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752001"
---
# <a name="params-c-reference"></a><span data-ttu-id="65942-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="65942-102">params (C# Reference)</span></span>
<span data-ttu-id="65942-103">С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="65942-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="65942-104">Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="65942-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="65942-105">Можно также не отправлять аргументы.</span><span class="sxs-lookup"><span data-stu-id="65942-105">You also can send no arguments.</span></span> <span data-ttu-id="65942-106">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="65942-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="65942-107">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="65942-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
 
 <span data-ttu-id="65942-108">Объявленный тип параметра `params` должен быть одномерным массивом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="65942-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="65942-109">В противном случае возникает ошибка компилятора [CS0225](../../../csharp/misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="65942-109">Otherwise, a compiler error [CS0225](../../../csharp/misc/cs0225.md) occurs.</span></span>
  
## <a name="example"></a><span data-ttu-id="65942-110">Пример</span><span class="sxs-lookup"><span data-stu-id="65942-110">Example</span></span>  
 <span data-ttu-id="65942-111">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="65942-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="65942-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="65942-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65942-113">См. также</span><span class="sxs-lookup"><span data-stu-id="65942-113">See Also</span></span>  
 [<span data-ttu-id="65942-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="65942-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="65942-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="65942-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="65942-116">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="65942-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="65942-117">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="65942-117">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
