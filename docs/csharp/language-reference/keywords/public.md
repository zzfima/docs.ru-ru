---
title: Справочник по C#. Ключевое слово public
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 15b86920736f1220553b462d103841ac98d88b7c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239307"
---
# <a name="public-c-reference"></a><span data-ttu-id="a5edb-102">public (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a5edb-102">public (C# Reference)</span></span>

<span data-ttu-id="a5edb-103">Ключевое слово `public` является модификатором доступа для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="a5edb-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="a5edb-104">Общий доступ является уровнем доступа с максимальными правами.</span><span class="sxs-lookup"><span data-stu-id="a5edb-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="a5edb-105">Ограничений доступа к общим членам не существует, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a5edb-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="a5edb-106">Дополнительные сведения см. в разделах [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a5edb-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="a5edb-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a5edb-107">Example</span></span>

<span data-ttu-id="a5edb-108">В следующем примере объявляются два класса: `PointTest` и `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="a5edb-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="a5edb-109">Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="a5edb-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="a5edb-110">Если уровень доступа `public` изменить на [private](private.md) или [protected](protected.md), будет выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a5edb-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="a5edb-111">"PointTest.y" недоступен из-за его уровня защиты.</span><span class="sxs-lookup"><span data-stu-id="a5edb-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a5edb-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a5edb-112">C# language specification</span></span>  

<span data-ttu-id="a5edb-113">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5edb-113">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="a5edb-114">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="a5edb-114">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5edb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a5edb-115">See also</span></span>

- [<span data-ttu-id="a5edb-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a5edb-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5edb-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a5edb-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a5edb-118">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="a5edb-118">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a5edb-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a5edb-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a5edb-120">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="a5edb-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a5edb-121">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="a5edb-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a5edb-122">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a5edb-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="a5edb-123">private</span><span class="sxs-lookup"><span data-stu-id="a5edb-123">private</span></span>](private.md)
- [<span data-ttu-id="a5edb-124">protected</span><span class="sxs-lookup"><span data-stu-id="a5edb-124">protected</span></span>](protected.md)
- [<span data-ttu-id="a5edb-125">internal</span><span class="sxs-lookup"><span data-stu-id="a5edb-125">internal</span></span>](internal.md)