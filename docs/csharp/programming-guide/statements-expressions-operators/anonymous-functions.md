---
title: Руководство по программированию на C#. Анонимные функции
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 4d266584e1867a512e4b61e8839fe948aafb007f
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363916"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="ff427-102">Руководство по программированию на C#. Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="ff427-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="ff427-103">Анонимная функция — это "встроенный" оператор или выражение, которое может использоваться, когда тип делегата неизвестен.</span><span class="sxs-lookup"><span data-stu-id="ff427-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="ff427-104">Ее можно использовать для инициализации именованного делегата или передать вместо типа именованного делегата в качестве параметра метода.</span><span class="sxs-lookup"><span data-stu-id="ff427-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="ff427-105">Для создания анонимной функции можно использовать [лямбда-выражение](lambda-expressions.md) или [анонимный метод](../../language-reference/operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ff427-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="ff427-106">Мы советуем использовать лямбда-выражения, так как это более лаконичный способ написания встроенного кода.</span><span class="sxs-lookup"><span data-stu-id="ff427-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="ff427-107">В отличие от анонимных методов некоторые типы лямбда-выражений можно преобразовывать в типы дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="ff427-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="ff427-108">Эволюция делегатов в C\#</span><span class="sxs-lookup"><span data-stu-id="ff427-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="ff427-109">В C# 1.0 экземпляр делегата создавался путем его явной инициализации с помощью метода, который был определен в другом месте кода.</span><span class="sxs-lookup"><span data-stu-id="ff427-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="ff427-110">В C# 2.0 введена концепция анонимных методов как способа написания неименованных встроенных блоков операторов, которые могут быть выполнены в вызове делегата.</span><span class="sxs-lookup"><span data-stu-id="ff427-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="ff427-111">В C# 3.0 введены лямбда-выражения, по сути аналогичные анонимным методам, но более выразительные и четкие.</span><span class="sxs-lookup"><span data-stu-id="ff427-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="ff427-112">Эти две функции собирательно называют *анонимными функциями*.</span><span class="sxs-lookup"><span data-stu-id="ff427-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="ff427-113">Как правило, приложения, предназначенные для версии 3.5 и более поздних версий платформы .NET Framework, должны использовать лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="ff427-113">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="ff427-114">В следующем примере демонстрируется эволюция создания делегата от C# 1.0 до C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="ff427-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ff427-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ff427-115">C# language specification</span></span>

<span data-ttu-id="ff427-116">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ff427-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff427-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ff427-117">See also</span></span>

- [<span data-ttu-id="ff427-118">Инструкции, выражения и операторы</span><span class="sxs-lookup"><span data-stu-id="ff427-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="ff427-119">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="ff427-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="ff427-120">Делегаты</span><span class="sxs-lookup"><span data-stu-id="ff427-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- <span data-ttu-id="ff427-121">[Expression Trees (C#)](../concepts/expression-trees/index.md) (Деревья выражений (C#))</span><span class="sxs-lookup"><span data-stu-id="ff427-121">[Expression Trees (C#)](../concepts/expression-trees/index.md)</span></span>
