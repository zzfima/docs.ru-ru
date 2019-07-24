---
title: Справочник по C#. Оператор nameof
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 965b3e96a20906187df4c8693f050c550a747091
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331435"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="6b89f-102">Справочник по C#. Оператор nameof</span><span class="sxs-lookup"><span data-stu-id="6b89f-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="6b89f-103">Оператор `nameof` получает имя, тип или член переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="6b89f-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="6b89f-104">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="6b89f-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="6b89f-105">Оператор `nameof` вычисляется во время компиляции и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b89f-105">The `nameof` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="6b89f-106">С помощью оператора `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="6b89f-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="6b89f-107">Оператор `nameof` доступен в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="6b89f-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6b89f-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6b89f-108">C# language specification</span></span>

<span data-ttu-id="6b89f-109">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6b89f-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b89f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6b89f-110">See also</span></span>

- [<span data-ttu-id="6b89f-111">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6b89f-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6b89f-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="6b89f-112">C# operators</span></span>](index.md)
