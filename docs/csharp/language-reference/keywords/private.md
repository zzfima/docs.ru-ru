---
title: Справочник по C#. Ключевое слово private
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 19e2925cd65cc9c68ff50d370398a4f401275940
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422594"
---
# <a name="private-c-reference"></a><span data-ttu-id="a3765-102">private (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a3765-102">private (C# Reference)</span></span>

<span data-ttu-id="a3765-103">Ключевое слово `private` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="a3765-103">The `private` keyword is a member access modifier.</span></span>

> <span data-ttu-id="a3765-104">Эта страница содержит доступ `private`.</span><span class="sxs-lookup"><span data-stu-id="a3765-104">This page covers `private` access.</span></span> <span data-ttu-id="a3765-105">Ключевое слово `private` также является частью модификатора доступа [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a3765-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>

<span data-ttu-id="a3765-106">Закрытый доступ является уровнем доступа с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="a3765-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="a3765-107">Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a3765-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

<span data-ttu-id="a3765-108">Вложенные типы в том же теле могут также обращаться к таким закрытым членам.</span><span class="sxs-lookup"><span data-stu-id="a3765-108">Nested types in the same body can also access those private members.</span></span>

<span data-ttu-id="a3765-109">Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.</span><span class="sxs-lookup"><span data-stu-id="a3765-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>

<span data-ttu-id="a3765-110">Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](accessibility-levels.md) и [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a3765-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3765-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a3765-111">Example</span></span>

<span data-ttu-id="a3765-112">В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`.</span><span class="sxs-lookup"><span data-stu-id="a3765-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="a3765-113">Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов.</span><span class="sxs-lookup"><span data-stu-id="a3765-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="a3765-114">Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`.</span><span class="sxs-lookup"><span data-stu-id="a3765-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="a3765-115">Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a3765-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="a3765-116">(Дополнительные сведения см. в разделе [Свойства](../../programming-guide/classes-and-structs/properties.md).)</span><span class="sxs-lookup"><span data-stu-id="a3765-116">(See [Properties](../../programming-guide/classes-and-structs/properties.md) for more information.)</span></span>

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a><span data-ttu-id="a3765-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a3765-117">C# language specification</span></span>  

<span data-ttu-id="a3765-118">Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a3765-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a3765-119">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="a3765-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3765-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a3765-120">See also</span></span>

- [<span data-ttu-id="a3765-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a3765-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3765-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a3765-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3765-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a3765-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a3765-124">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="a3765-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a3765-125">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="a3765-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a3765-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="a3765-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a3765-127">public</span><span class="sxs-lookup"><span data-stu-id="a3765-127">public</span></span>](public.md)
- [<span data-ttu-id="a3765-128">protected</span><span class="sxs-lookup"><span data-stu-id="a3765-128">protected</span></span>](protected.md)
- [<span data-ttu-id="a3765-129">internal</span><span class="sxs-lookup"><span data-stu-id="a3765-129">internal</span></span>](internal.md)
