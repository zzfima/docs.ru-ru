---
title: Справочник по C#. Оператор try-catch-finally
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 787005ec09a2c5c4f0e5033c83fd6a7ab7875b7e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422167"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="844eb-102">try-catch-finally (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="844eb-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="844eb-103">Чаще всего `catch` и `finally` применяются вместе для получения и использования ресурсов в блоке `try`, устранения исключительных обстоятельств в блоке `catch` и освобождения ресурсов в блоке `finally`.</span><span class="sxs-lookup"><span data-stu-id="844eb-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="844eb-104">Дополнительные сведения и примеры повторного создания исключений см. в разделах [try-catch](try-catch.md) и [Порождение исключений](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="844eb-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="844eb-105">Дополнительные сведения о блоке `finally` см. в разделе [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="844eb-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="844eb-106">Пример</span><span class="sxs-lookup"><span data-stu-id="844eb-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="844eb-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="844eb-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="844eb-108">См. также</span><span class="sxs-lookup"><span data-stu-id="844eb-108">See also</span></span>

- [<span data-ttu-id="844eb-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="844eb-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="844eb-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="844eb-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="844eb-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="844eb-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="844eb-112">Операторы try, throw и catch (C++)</span><span class="sxs-lookup"><span data-stu-id="844eb-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="844eb-113">throw</span><span class="sxs-lookup"><span data-stu-id="844eb-113">throw</span></span>](throw.md)
- [<span data-ttu-id="844eb-114">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="844eb-114">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="844eb-115">Оператор using</span><span class="sxs-lookup"><span data-stu-id="844eb-115">using Statement</span></span>](using-statement.md)
