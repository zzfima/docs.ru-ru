---
title: Выражение nameof. Справочник по C#
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507143"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="044a1-102">Выражение nameof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="044a1-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="044a1-103">Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="044a1-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="044a1-104">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="044a1-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="044a1-105">Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="044a1-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="044a1-106">С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="044a1-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="044a1-107">Выражение `nameof` доступно в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="044a1-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="044a1-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="044a1-108">C# language specification</span></span>

<span data-ttu-id="044a1-109">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="044a1-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="044a1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="044a1-110">See also</span></span>

- [<span data-ttu-id="044a1-111">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="044a1-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="044a1-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="044a1-112">C# operators</span></span>](index.md)
