---
title: "params (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66cfc8e7b131a4443ee227df5e39c7e3b775324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="params-c-reference"></a><span data-ttu-id="33ef8-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="33ef8-102">params (C# Reference)</span></span>
<span data-ttu-id="33ef8-103">С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="33ef8-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="33ef8-104">Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="33ef8-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="33ef8-105">Можно также не отправлять аргументы.</span><span class="sxs-lookup"><span data-stu-id="33ef8-105">You also can send no arguments.</span></span> <span data-ttu-id="33ef8-106">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="33ef8-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="33ef8-107">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="33ef8-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33ef8-108">Пример</span><span class="sxs-lookup"><span data-stu-id="33ef8-108">Example</span></span>  
 <span data-ttu-id="33ef8-109">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="33ef8-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="33ef8-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="33ef8-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33ef8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="33ef8-111">See Also</span></span>  
 [<span data-ttu-id="33ef8-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="33ef8-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="33ef8-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="33ef8-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="33ef8-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="33ef8-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="33ef8-115">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="33ef8-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
