---
title: Вложенные типы (Руководство по программированию на C#)
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 57356fbf4bff218932d1f1b4c62532f10c175757
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319937"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="2f9f0-102">Вложенные типы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2f9f0-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="2f9f0-103">Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="2f9f0-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="2f9f0-104">For example:</span></span>  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
<span data-ttu-id="2f9f0-105">Независимо от того, является ли внешний тип классом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../../csharp/language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="2f9f0-106">В предыдущем примере класс `Nested` недоступен для внешних типов.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="2f9f0-107">Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2f9f0-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="2f9f0-108">Вложенные типы **класса** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="2f9f0-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="2f9f0-109">Тем не менее при определении вложенного класса `protected`, `protected internal` или `private protected` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".</span><span class="sxs-lookup"><span data-stu-id="2f9f0-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="2f9f0-110">Вложенные типы **структуры** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="2f9f0-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="2f9f0-111">В следующем примере класс `Nested` определяется как открытый:</span><span class="sxs-lookup"><span data-stu-id="2f9f0-111">The following example makes the `Nested` class public:</span></span>
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 <span data-ttu-id="2f9f0-112">Вложенный (внутренний) тип может получить доступ к вмещающему (внешнему) типу.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="2f9f0-113">Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="2f9f0-114">Пример: </span><span class="sxs-lookup"><span data-stu-id="2f9f0-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 <span data-ttu-id="2f9f0-115">Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="2f9f0-116">Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="2f9f0-117">В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="2f9f0-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="2f9f0-118">Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2f9f0-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2f9f0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2f9f0-119">See Also</span></span>  
 [<span data-ttu-id="2f9f0-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2f9f0-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2f9f0-121">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="2f9f0-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="2f9f0-122">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="2f9f0-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="2f9f0-123">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="2f9f0-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
