---
title: Руководство по программированию на C#. Вложенные типы
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 12e44ccc1254424c152a238c8390f133550fa54c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626494"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="e34b5-102">Вложенные типы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e34b5-102">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="e34b5-103">Тип, определенный внутри [класса](../../language-reference/keywords/class.md), [структуры](../../language-reference/builtin-types/struct.md) или [интерфейса](../../language-reference/keywords/interface.md), называется вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="e34b5-103">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="e34b5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e34b5-104">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="e34b5-105">Независимо от того, является ли внешний тип классом, интерфейсом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа.</span><span class="sxs-lookup"><span data-stu-id="e34b5-105">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="e34b5-106">В предыдущем примере класс `Nested` недоступен для внешних типов.</span><span class="sxs-lookup"><span data-stu-id="e34b5-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="e34b5-107">Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e34b5-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="e34b5-108">Вложенные типы **класса** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) или [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="e34b5-108">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="e34b5-109">Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".</span><span class="sxs-lookup"><span data-stu-id="e34b5-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="e34b5-110">Вложенные типы **структуры** могут иметь модификаторы [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) или [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="e34b5-110">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="e34b5-111">В следующем примере класс `Nested` определяется как открытый:</span><span class="sxs-lookup"><span data-stu-id="e34b5-111">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="e34b5-112">Вложенный (внутренний) тип может получить доступ к вмещающему (внешнему) типу.</span><span class="sxs-lookup"><span data-stu-id="e34b5-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="e34b5-113">Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="e34b5-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="e34b5-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="e34b5-114">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="e34b5-115">Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.</span><span class="sxs-lookup"><span data-stu-id="e34b5-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="e34b5-116">Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="e34b5-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="e34b5-117">В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="e34b5-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="e34b5-118">Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e34b5-118">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="e34b5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e34b5-119">See also</span></span>

- [<span data-ttu-id="e34b5-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e34b5-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e34b5-121">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="e34b5-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="e34b5-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="e34b5-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="e34b5-123">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="e34b5-123">Constructors</span></span>](./constructors.md)
