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
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265474"
---
# <a name="params-c-reference"></a><span data-ttu-id="8e998-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8e998-102">params (C# Reference)</span></span>
<span data-ttu-id="8e998-103">С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="8e998-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="8e998-104">Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="8e998-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="8e998-105">Можно также не отправлять аргументы.</span><span class="sxs-lookup"><span data-stu-id="8e998-105">You also can send no arguments.</span></span> <span data-ttu-id="8e998-106">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="8e998-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="8e998-107">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="8e998-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e998-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8e998-108">Example</span></span>  
 <span data-ttu-id="8e998-109">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="8e998-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8e998-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8e998-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e998-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8e998-111">See Also</span></span>  
 [<span data-ttu-id="8e998-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8e998-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8e998-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8e998-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e998-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="8e998-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8e998-115">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="8e998-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
