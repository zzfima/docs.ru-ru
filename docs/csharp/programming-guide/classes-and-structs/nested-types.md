---
title: "Вложенные типы (Руководство по программированию на C#)"
ms.date: 2017-07-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 853ec746d9be01ed63d7a229ca86e99d9f192374
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="e9631-102">Вложенные типы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e9631-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="e9631-103">Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="e9631-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="e9631-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9631-104">For example:</span></span>  
  
<span data-ttu-id="e9631-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9631-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span></span>  
  
<span data-ttu-id="e9631-106">Независимо от того, является ли внешний тип классом или структурой, вложенным типам по умолчанию присваивается модификатор [private](../../../csharp/language-reference/keywords/private.md), из-за чего они доступны только из содержащего их типа.</span><span class="sxs-lookup"><span data-stu-id="e9631-106">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="e9631-107">В предыдущем примере класс `Nested` недоступен для внешних типов.</span><span class="sxs-lookup"><span data-stu-id="e9631-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="e9631-108">Также можно указать [модификатор доступа](../../language-reference/keywords/access-modifiers.md), определяющий доступность вложенного типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e9631-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="e9631-109">Вложенные типы **класса** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal` или [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="e9631-109">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal`, or [private](../../../csharp/language-reference/keywords/private.md).</span></span> 

   <span data-ttu-id="e9631-110">Тем не менее при определении вложенного класса `protected` или `protected internal` внутри [запечатанного класса](../../language-reference/keywords/sealed.md) возникает предупреждение компилятора [CS0628](../../misc/cs0628.md) "Новый защищенный член объявлен в запечатанном классе".</span><span class="sxs-lookup"><span data-stu-id="e9631-110">However, defining a `protected` or `protected internal` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="e9631-111">Вложенные типы **структуры** могут иметь модификаторы [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="e9631-111">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="e9631-112">В следующем примере класс `Nested` определяется как открытый:</span><span class="sxs-lookup"><span data-stu-id="e9631-112">The following example makes the `Nested` class public:</span></span>
  
<span data-ttu-id="e9631-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9631-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span></span>  
  
 <span data-ttu-id="e9631-114">Вложенный тип может получить доступ к вмещающему типу, а внутренний тип — к внешнему.</span><span class="sxs-lookup"><span data-stu-id="e9631-114">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="e9631-115">Чтобы получить доступ к вмещающему типу, передайте его в качестве аргумента в конструктор вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="e9631-115">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="e9631-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9631-116">For example:</span></span>  
  
 <span data-ttu-id="e9631-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9631-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span></span>  
  
 <span data-ttu-id="e9631-118">Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.</span><span class="sxs-lookup"><span data-stu-id="e9631-118">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="e9631-119">Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.</span><span class="sxs-lookup"><span data-stu-id="e9631-119">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="e9631-120">В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="e9631-120">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="e9631-121">Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e9631-121">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 <span data-ttu-id="e9631-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9631-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9631-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e9631-123">See Also</span></span>  
 <span data-ttu-id="e9631-124">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9631-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e9631-125">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9631-125">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="e9631-126">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="e9631-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="e9631-127">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="e9631-127">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

