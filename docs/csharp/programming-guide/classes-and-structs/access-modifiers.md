---
title: "Модификаторы доступа (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="fd333-102">Модификаторы доступа (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="fd333-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="fd333-103">Все типы и члены имеют уровень доступности, определяющий возможность их использования из другого кода в вашей или в других сборках.</span><span class="sxs-lookup"><span data-stu-id="fd333-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="fd333-104">Следующие модификаторы доступа позволяют указать доступность типа или члена при объявлении:</span><span class="sxs-lookup"><span data-stu-id="fd333-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="fd333-105">public</span><span class="sxs-lookup"><span data-stu-id="fd333-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="fd333-106">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="fd333-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="fd333-107">private</span><span class="sxs-lookup"><span data-stu-id="fd333-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="fd333-108">Доступ к типу или члену возможен только из кода в том же классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="fd333-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="fd333-109">protected</span><span class="sxs-lookup"><span data-stu-id="fd333-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="fd333-110">Доступ к типу или члену возможен только из кода в том же классе или структуре либо в классе, производном от этого класса.</span><span class="sxs-lookup"><span data-stu-id="fd333-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="fd333-111">internal</span><span class="sxs-lookup"><span data-stu-id="fd333-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="fd333-112">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="fd333-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="fd333-113">Доступ к типу или члену возможен из любого кода в той сборке, где он был объявлен, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="fd333-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="fd333-114">Доступ из другой сборки должен осуществляться в объявлении класса, производного от класса, в котором объявлен защищенный внутренний элемент, и через экземпляр типа производного класса.</span><span class="sxs-lookup"><span data-stu-id="fd333-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="fd333-115">В следующих примерах показано, как изменить модификаторы доступа для типа или члена типа:</span><span class="sxs-lookup"><span data-stu-id="fd333-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="fd333-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fd333-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="fd333-117">Не все модификаторы доступа могут использоваться всеми типами или членами типов во всех контекстах, а в некоторых случаях доступность члена типа ограничивается доступностью типа, в котором он содержится.</span><span class="sxs-lookup"><span data-stu-id="fd333-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="fd333-118">Следующие подразделы содержат дополнительные сведения о доступности.</span><span class="sxs-lookup"><span data-stu-id="fd333-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="fd333-119">Доступность классов и структур</span><span class="sxs-lookup"><span data-stu-id="fd333-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="fd333-120">Классы и структуры, объявленные непосредственно в пространстве имен (другими словами, не вложенные в другие классы или структуры), могут быть открытыми или внутренними.</span><span class="sxs-lookup"><span data-stu-id="fd333-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="fd333-121">Если модификатор доступа не указан, по умолчанию используется внутренний тип.</span><span class="sxs-lookup"><span data-stu-id="fd333-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="fd333-122">Члены структуры, включая вложенные классы и структуры, могут объявляться как открытые, внутренние или закрытые.</span><span class="sxs-lookup"><span data-stu-id="fd333-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="fd333-123">Члены класса, включая вложенные классы и структуры, могут объявляться как открытые, защищенные внутренние, защищенные, внутренние или закрытые.</span><span class="sxs-lookup"><span data-stu-id="fd333-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="fd333-124">По умолчанию уровень доступа к членам класса и членам структуры, включая вложенные классы и структуры, является закрытым.</span><span class="sxs-lookup"><span data-stu-id="fd333-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="fd333-125">Закрытые вложенные типы недоступны за пределами типа, в котором содержатся.</span><span class="sxs-lookup"><span data-stu-id="fd333-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="fd333-126">Производные классы не могут быть более доступны, чем соответствующие базовые типы.</span><span class="sxs-lookup"><span data-stu-id="fd333-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="fd333-127">Другими словами, нельзя иметь открытый класс `B`, производный от внутреннего класса `A`.</span><span class="sxs-lookup"><span data-stu-id="fd333-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="fd333-128">Если бы это было возможно, класс `A` стал бы открытым, поскольку все защищенные или внутренние члены класса `A` были бы доступны из производного класса.</span><span class="sxs-lookup"><span data-stu-id="fd333-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="fd333-129">Доступ к внутренним типам можно предоставить некоторым другим сборкам с помощью класса InternalsVisibleToAttribute.</span><span class="sxs-lookup"><span data-stu-id="fd333-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="fd333-130">Дополнительные сведения см. в разделе [Дружественные сборки](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="fd333-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="fd333-131">Доступность членов классов и структур</span><span class="sxs-lookup"><span data-stu-id="fd333-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="fd333-132">Члены класса (включая вложенные классы и структуры) можно объявлять с любым из пяти типов доступа.</span><span class="sxs-lookup"><span data-stu-id="fd333-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="fd333-133">Члены структуры нельзя объявлять как защищенные, поскольку структуры не поддерживают наследование.</span><span class="sxs-lookup"><span data-stu-id="fd333-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="fd333-134">Как правило, уровень доступности члена не может быть выше уровня доступности типа, в который он входит.</span><span class="sxs-lookup"><span data-stu-id="fd333-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="fd333-135">При этом открытый член внутреннего класса может быть доступен за пределами сборки, если он реализует методы интерфейса или переопределяет виртуальные методы, определенные в открытом базовом классе.</span><span class="sxs-lookup"><span data-stu-id="fd333-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="fd333-136">Тип любого члена, который является полем, свойством или событием, должен иметь, как минимум, такой же уровень доступности, как у самого члена.</span><span class="sxs-lookup"><span data-stu-id="fd333-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="fd333-137">Точно так же тип возвращаемого значения и типы параметров любого члена, который является методом, индексатором или делегатом, должен иметь, как минимум, такой же уровень доступности, как у самого члена.</span><span class="sxs-lookup"><span data-stu-id="fd333-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="fd333-138">Например, нельзя иметь открытый метод `M`, возвращающий класс `C`, если `C` не является также открытым.</span><span class="sxs-lookup"><span data-stu-id="fd333-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="fd333-139">Аналогичным образом нельзя иметь защищенное свойство типа `A`, если `A` объявлен как закрытый.</span><span class="sxs-lookup"><span data-stu-id="fd333-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="fd333-140">Пользовательские операторы всегда должны объявляться как открытые.</span><span class="sxs-lookup"><span data-stu-id="fd333-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="fd333-141">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="fd333-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="fd333-142">Методы завершения не могут иметь модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="fd333-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="fd333-143">Чтобы настроить уровень доступа для члена класса или структуры, добавьте в объявление этого члена соответствующее ключевое слово, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fd333-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fd333-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fd333-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd333-145">Защищенный внутренний уровень доступности означает защищенный ИЛИ внутренний доступ, а не защищенный И внутренний.</span><span class="sxs-lookup"><span data-stu-id="fd333-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="fd333-146">Другими словами, защищенный внутренний член доступен из любого класса в той же сборке, включая производные классы.</span><span class="sxs-lookup"><span data-stu-id="fd333-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="fd333-147">Чтобы сделать его доступным только для производных классов в той же сборке, объявите сам класс как внутренний, а его члены как защищенные.</span><span class="sxs-lookup"><span data-stu-id="fd333-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="fd333-148">Другие типы</span><span class="sxs-lookup"><span data-stu-id="fd333-148">Other Types</span></span>  
 <span data-ttu-id="fd333-149">Интерфейсы, объявляемые непосредственно в пространстве имен, могут быть объявлены как открытые или внутренние. Равно как и в случае с классами и структурами, для интерфейсов по умолчанию задается внутренний доступ.</span><span class="sxs-lookup"><span data-stu-id="fd333-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="fd333-150">Члены интерфейса всегда открыты, поскольку интерфейс как раз и создан для того, чтобы обеспечить доступ к классу или структуре для других типов.</span><span class="sxs-lookup"><span data-stu-id="fd333-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="fd333-151">Модификаторы доступа к членам интерфейса не применяются.</span><span class="sxs-lookup"><span data-stu-id="fd333-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="fd333-152">Члены перечисления всегда открыты, и модификаторы доступа к ним не применяются.</span><span class="sxs-lookup"><span data-stu-id="fd333-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="fd333-153">Делегаты ведут себя как классы и структуры.</span><span class="sxs-lookup"><span data-stu-id="fd333-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="fd333-154">По умолчанию они имеют внутренний доступ, если объявляются непосредственно в пространстве имен, и закрытый доступ, если являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="fd333-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fd333-155">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fd333-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd333-156">См. также</span><span class="sxs-lookup"><span data-stu-id="fd333-156">See Also</span></span>  
 <span data-ttu-id="fd333-157">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fd333-158">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="fd333-159">[Интерфейсы](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="fd333-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="fd333-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="fd333-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="fd333-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="fd333-164">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="fd333-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="fd333-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="fd333-166">interface</span><span class="sxs-lookup"><span data-stu-id="fd333-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

