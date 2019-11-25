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
ms.openlocfilehash: fa858db918cdaf04c757f2741265e359acb74f7b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036351"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="b96a5-102">Справочник по C#. Оператор nameof</span><span class="sxs-lookup"><span data-stu-id="b96a5-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="b96a5-103">Оператор `nameof` получает имя, тип или член переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="b96a5-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="b96a5-104">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="b96a5-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="b96a5-105">Оператор `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b96a5-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="b96a5-106">С помощью оператора `nameof` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="b96a5-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="b96a5-107">Оператор `nameof` доступен в C# версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="b96a5-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b96a5-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b96a5-108">C# language specification</span></span>

<span data-ttu-id="b96a5-109">См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b96a5-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b96a5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b96a5-110">See also</span></span>

- [<span data-ttu-id="b96a5-111">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b96a5-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b96a5-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b96a5-112">C# operators</span></span>](index.md)
