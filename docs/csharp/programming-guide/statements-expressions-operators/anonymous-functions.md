---
title: Руководство по программированию на C#. Анонимные функции
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 338f4b34a5de84d4ce2eb9e0bd6f4c9ebe360fa4
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584275"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="18c62-102">Анонимные функции (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="18c62-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="18c62-103">Анонимная функция — это "встроенный" оператор или выражение, которое может использоваться, когда тип делегата неизвестен.</span><span class="sxs-lookup"><span data-stu-id="18c62-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="18c62-104">Ее можно использовать для инициализации именованного делегата или передать вместо типа именованного делегата в качестве параметра метода.</span><span class="sxs-lookup"><span data-stu-id="18c62-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="18c62-105">Существует два типа анонимных функций, которые по отдельности рассматриваются в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="18c62-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
- <span data-ttu-id="18c62-106">[Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="18c62-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
- [<span data-ttu-id="18c62-107">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="18c62-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="18c62-108">Лямбда-выражения могут быть привязаны к деревьям выражений и к делегатам.</span><span class="sxs-lookup"><span data-stu-id="18c62-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="18c62-109">Эволюция делегатов в C\#</span><span class="sxs-lookup"><span data-stu-id="18c62-109">The Evolution of Delegates in C\#</span></span>
 <span data-ttu-id="18c62-110">В C# 1.0 экземпляр делегата создавался путем его явной инициализации с помощью метода, который был определен в другом месте кода.</span><span class="sxs-lookup"><span data-stu-id="18c62-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="18c62-111">В C# 2.0 введена концепция анонимных методов как способа написания неименованных встроенных блоков операторов, которые могут быть выполнены в вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="18c62-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="18c62-112">В C# 3.0 введены лямбда-выражения, по сути аналогичные анонимным методам, но более выразительные и четкие.</span><span class="sxs-lookup"><span data-stu-id="18c62-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="18c62-113">Эти две функции собирательно называют *анонимными функциями*.</span><span class="sxs-lookup"><span data-stu-id="18c62-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="18c62-114">Как правило, приложения, предназначенные для версии 3.5 и более поздних версий платформы .NET Framework, должны использовать лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="18c62-114">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="18c62-115">В следующем примере демонстрируется эволюция создания делегата от C# 1.0 до C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="18c62-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="18c62-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="18c62-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18c62-117">См. также</span><span class="sxs-lookup"><span data-stu-id="18c62-117">See also</span></span>

- [<span data-ttu-id="18c62-118">Инструкции, выражения и операторы</span><span class="sxs-lookup"><span data-stu-id="18c62-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="18c62-119">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="18c62-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="18c62-120">Делегаты</span><span class="sxs-lookup"><span data-stu-id="18c62-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- <span data-ttu-id="18c62-121">[Expression Trees (C#)](../concepts/expression-trees/index.md) (Деревья выражений (C#))</span><span class="sxs-lookup"><span data-stu-id="18c62-121">[Expression Trees (C#)](../concepts/expression-trees/index.md)</span></span>
