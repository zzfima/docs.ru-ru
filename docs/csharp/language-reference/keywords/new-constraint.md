---
title: Ограничение new. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 7c788be52010cdfadbd3c03f9e570815d25bdbef
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401484"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="11bb0-102">Ограничение new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="11bb0-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="11bb0-103">Ограничение `new` указывает, что аргумент типа в объявлении универсального класса должен иметь открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="11bb0-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="11bb0-104">Использовать ограничение `new` можно только в том случае, если тип не является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="11bb0-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="11bb0-105">Примените ограничение `new` к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="11bb0-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="11bb0-106">При использовании ограничения `new()` с другими ограничениями его необходимо указывать последним:</span><span class="sxs-lookup"><span data-stu-id="11bb0-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="11bb0-107">Дополнительные сведения см. в разделе [Ограничения параметров типа](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="11bb0-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="11bb0-108">Ключевое слово `new` можно также использовать для [создания экземпляра типа](../operators/new-operator.md) или как [модификатор объявления члена](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="11bb0-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="11bb0-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="11bb0-109">C# language specification</span></span>

<span data-ttu-id="11bb0-110">Дополнительные сведения см. в разделе [Ограничения параметров типа](~/_csharplang/spec/classes.md#type-parameter-constraints) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="11bb0-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11bb0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="11bb0-111">See also</span></span>

- [<span data-ttu-id="11bb0-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="11bb0-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="11bb0-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="11bb0-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="11bb0-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="11bb0-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="11bb0-115">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="11bb0-115">Generics</span></span>](../../programming-guide/generics/index.md)
