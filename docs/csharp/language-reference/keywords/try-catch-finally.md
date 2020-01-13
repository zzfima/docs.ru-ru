---
title: Справочник по C#. Оператор try-catch-finally
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 5d98f6967595c7c32b23ba5422a8d9ca79f7f54c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713044"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="6f76a-102">try-catch-finally (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6f76a-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="6f76a-103">Чаще всего `catch` и `finally` применяются вместе для получения и использования ресурсов в блоке `try`, устранения исключительных обстоятельств в блоке `catch` и освобождения ресурсов в блоке `finally`.</span><span class="sxs-lookup"><span data-stu-id="6f76a-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="6f76a-104">Дополнительные сведения и примеры повторного создания исключений см. в разделах [try-catch](try-catch.md) и [Порождение исключений](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f76a-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="6f76a-105">Дополнительные сведения о блоке `finally` см. в разделе [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="6f76a-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="6f76a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6f76a-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="6f76a-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6f76a-107">C# language specification</span></span>

<span data-ttu-id="6f76a-108">Дополнительные сведения см. в разделе [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в документации [Спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6f76a-108">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f76a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6f76a-109">See also</span></span>

- [<span data-ttu-id="6f76a-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6f76a-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6f76a-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6f76a-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6f76a-112">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6f76a-112">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6f76a-113">Операторы try, throw и catch (C++)</span><span class="sxs-lookup"><span data-stu-id="6f76a-113">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="6f76a-114">throw</span><span class="sxs-lookup"><span data-stu-id="6f76a-114">throw</span></span>](throw.md)
- [<span data-ttu-id="6f76a-115">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="6f76a-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="6f76a-116">Оператор using</span><span class="sxs-lookup"><span data-stu-id="6f76a-116">using Statement</span></span>](using-statement.md)
