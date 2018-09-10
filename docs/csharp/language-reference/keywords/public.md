---
title: Ключевое слово public (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484161"
---
# <a name="public-c-reference"></a><span data-ttu-id="0dc88-102">public (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0dc88-102">public (C# Reference)</span></span>

<span data-ttu-id="0dc88-103">Ключевое слово `public` является модификатором доступа для типов и членов типов.</span><span class="sxs-lookup"><span data-stu-id="0dc88-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="0dc88-104">Общий доступ является уровнем доступа с максимальными правами.</span><span class="sxs-lookup"><span data-stu-id="0dc88-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="0dc88-105">Ограничений доступа к общим членам не существует, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0dc88-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="0dc88-106">Дополнительные сведения см. в разделах [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0dc88-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="0dc88-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0dc88-107">Example</span></span>

<span data-ttu-id="0dc88-108">В следующем примере объявляются два класса: `PointTest` и `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="0dc88-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="0dc88-109">Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="0dc88-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="0dc88-110">Если уровень доступа `public` изменить на [private](private.md) или [protected](protected.md), будет выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="0dc88-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="0dc88-111">"PointTest.y" недоступен из-за его уровня защиты.</span><span class="sxs-lookup"><span data-stu-id="0dc88-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0dc88-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0dc88-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0dc88-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0dc88-113">See also</span></span>

- [<span data-ttu-id="0dc88-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0dc88-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0dc88-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0dc88-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0dc88-116">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="0dc88-116">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="0dc88-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0dc88-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0dc88-118">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="0dc88-118">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="0dc88-119">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="0dc88-119">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="0dc88-120">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="0dc88-120">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="0dc88-121">private</span><span class="sxs-lookup"><span data-stu-id="0dc88-121">private</span></span>](private.md)
- [<span data-ttu-id="0dc88-122">protected</span><span class="sxs-lookup"><span data-stu-id="0dc88-122">protected</span></span>](protected.md)
- [<span data-ttu-id="0dc88-123">internal</span><span class="sxs-lookup"><span data-stu-id="0dc88-123">internal</span></span>](internal.md)