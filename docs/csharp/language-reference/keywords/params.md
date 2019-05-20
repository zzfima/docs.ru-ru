---
title: Справочник по C#. Ключевое слово params
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 772c8da879eeccbe484c631a47de7fe8a32ec8d2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633581"
---
# <a name="params-c-reference"></a><span data-ttu-id="f5abc-102">params (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f5abc-102">params (C# Reference)</span></span>

<span data-ttu-id="f5abc-103">С помощью ключевого слова `params` можно указать [параметр метода](method-parameters.md), принимающий переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="f5abc-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="f5abc-104">Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа.</span><span class="sxs-lookup"><span data-stu-id="f5abc-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="f5abc-105">Можно также не отправлять аргументы.</span><span class="sxs-lookup"><span data-stu-id="f5abc-105">You also can send no arguments.</span></span> <span data-ttu-id="f5abc-106">Если аргументы не отправляются, длина списка `params` равна нулю.</span><span class="sxs-lookup"><span data-stu-id="f5abc-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="f5abc-107">В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.</span><span class="sxs-lookup"><span data-stu-id="f5abc-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="f5abc-108">Объявленный тип параметра `params` должен быть одномерным массивом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f5abc-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="f5abc-109">В противном случае возникает ошибка компилятора [CS0225](../../misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="f5abc-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="f5abc-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f5abc-110">Example</span></span>

<span data-ttu-id="f5abc-111">В следующем примере показаны различные способы оправки аргументов параметру `params`.</span><span class="sxs-lookup"><span data-stu-id="f5abc-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="f5abc-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f5abc-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f5abc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f5abc-113">See also</span></span>

- [<span data-ttu-id="f5abc-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f5abc-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f5abc-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f5abc-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f5abc-116">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f5abc-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f5abc-117">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="f5abc-117">Method Parameters</span></span>](method-parameters.md)
