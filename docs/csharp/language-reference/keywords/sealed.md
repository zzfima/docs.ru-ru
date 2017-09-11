---
title: "sealed (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
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
ms.openlocfilehash: a8d0fe959eac03aad4f1ae1fada61c0ad2fd65cd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="sealed-c-reference"></a><span data-ttu-id="52c03-102">sealed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="52c03-102">sealed (C# Reference)</span></span>
<span data-ttu-id="52c03-103">При применении к классу модификатор `sealed` запрещает другим классам наследовать от этого класса.</span><span class="sxs-lookup"><span data-stu-id="52c03-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="52c03-104">В следующем примере класс `B` наследует от класса `A`, но никакие классы не могут наследовать от класса `B`.</span><span class="sxs-lookup"><span data-stu-id="52c03-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="52c03-105">Модификатор `sealed` можно использовать для метода или свойства, которое переопределяет виртуальный метод или свойство в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="52c03-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="52c03-106">Это позволяет классам наследовать от вашего класса, запрещая им при этом переопределять определенные виртуальные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="52c03-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c03-107">Пример</span><span class="sxs-lookup"><span data-stu-id="52c03-107">Example</span></span>  
 <span data-ttu-id="52c03-108">В следующем примере класс `Z` наследует от класса `Y`, но `Z` не может переопределить виртуальную функцию `F`, которая объявлена в классе `X` и запечатана в классе `Y`.</span><span class="sxs-lookup"><span data-stu-id="52c03-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 <span data-ttu-id="52c03-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="52c03-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span></span>  
  
 <span data-ttu-id="52c03-110">Чтобы предотвратить переопределение производных классов при определении новых методов или свойств, не назначайте их в качестве виртуальных ([virtual](../../../csharp/language-reference/keywords/virtual.md)).</span><span class="sxs-lookup"><span data-stu-id="52c03-110">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="52c03-111">Нельзя использовать модификатор [abstract](../../../csharp/language-reference/keywords/abstract.md) с запечатанным классом, поскольку абстрактный класс должен наследоваться классом, реализующим абстрактные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="52c03-111">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="52c03-112">При применении к методу или свойству модификатор `sealed` всегда следует использовать с [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="52c03-112">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="52c03-113">Поскольку структуры неявно запечатаны, их нельзя наследовать.</span><span class="sxs-lookup"><span data-stu-id="52c03-113">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="52c03-114">Дополнительные сведения см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="52c03-114">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="52c03-115">Дополнительные примеры см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="52c03-115">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c03-116">Пример</span><span class="sxs-lookup"><span data-stu-id="52c03-116">Example</span></span>  
 <span data-ttu-id="52c03-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="52c03-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span></span>  
  
 <span data-ttu-id="52c03-118">Чтобы наследовать от запечатанного класса, можно применить следующую инструкцию в приведенном выше примере:</span><span class="sxs-lookup"><span data-stu-id="52c03-118">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="52c03-119">В результате выдается сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="52c03-119">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="52c03-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="52c03-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="52c03-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="52c03-121">Remarks</span></span>  
 <span data-ttu-id="52c03-122">Чтобы определить, нужно ли запечатывать класс, метод или свойство, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="52c03-122">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="52c03-123">потенциальные преимущества, которые производные классы могут получить от возможности настраивать ваш класс;</span><span class="sxs-lookup"><span data-stu-id="52c03-123">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="52c03-124">вероятность того, что производные классы могут корректировать ваши классы, препятствуя их нормальной работе.</span><span class="sxs-lookup"><span data-stu-id="52c03-124">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c03-125">См. также</span><span class="sxs-lookup"><span data-stu-id="52c03-125">See Also</span></span>  
 <span data-ttu-id="52c03-126">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="52c03-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="52c03-128">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="52c03-129">[Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-129">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 <span data-ttu-id="52c03-130">[Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-130">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="52c03-131">[Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-131">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="52c03-132">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-132">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="52c03-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="52c03-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="52c03-134">virtual</span><span class="sxs-lookup"><span data-stu-id="52c03-134">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)

