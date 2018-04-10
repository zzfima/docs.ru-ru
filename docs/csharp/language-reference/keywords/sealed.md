---
title: sealed (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8248b451f0431286fdaba3583fc2031eb6cdbcd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sealed-c-reference"></a><span data-ttu-id="e94b6-102">sealed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e94b6-102">sealed (C# Reference)</span></span>
<span data-ttu-id="e94b6-103">При применении к классу модификатор `sealed` запрещает другим классам наследовать от этого класса.</span><span class="sxs-lookup"><span data-stu-id="e94b6-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="e94b6-104">В следующем примере класс `B` наследует от класса `A`, но никакие классы не могут наследовать от класса `B`.</span><span class="sxs-lookup"><span data-stu-id="e94b6-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="e94b6-105">Модификатор `sealed` можно использовать для метода или свойства, которое переопределяет виртуальный метод или свойство в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="e94b6-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="e94b6-106">Это позволяет классам наследовать от вашего класса, запрещая им при этом переопределять определенные виртуальные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="e94b6-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e94b6-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e94b6-107">Example</span></span>  
 <span data-ttu-id="e94b6-108">В следующем примере класс `Z` наследует от класса `Y`, но `Z` не может переопределить виртуальную функцию `F`, которая объявлена в классе `X` и запечатана в классе `Y`.</span><span class="sxs-lookup"><span data-stu-id="e94b6-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 <span data-ttu-id="e94b6-109">Чтобы предотвратить переопределение производных классов при определении новых методов или свойств, не назначайте их в качестве виртуальных ([virtual](../../../csharp/language-reference/keywords/virtual.md)).</span><span class="sxs-lookup"><span data-stu-id="e94b6-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="e94b6-110">Нельзя использовать модификатор [abstract](../../../csharp/language-reference/keywords/abstract.md) с запечатанным классом, поскольку абстрактный класс должен наследоваться классом, реализующим абстрактные методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="e94b6-110">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="e94b6-111">При применении к методу или свойству модификатор `sealed` всегда следует использовать с [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="e94b6-111">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="e94b6-112">Поскольку структуры неявно запечатаны, их нельзя наследовать.</span><span class="sxs-lookup"><span data-stu-id="e94b6-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="e94b6-113">Дополнительные сведения см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="e94b6-113">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="e94b6-114">Дополнительные примеры см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="e94b6-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e94b6-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e94b6-115">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 <span data-ttu-id="e94b6-116">Чтобы наследовать от запечатанного класса, можно применить следующую инструкцию в приведенном выше примере:</span><span class="sxs-lookup"><span data-stu-id="e94b6-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="e94b6-117">В результате выдается сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="e94b6-117">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="e94b6-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e94b6-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="e94b6-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="e94b6-119">Remarks</span></span>  
 <span data-ttu-id="e94b6-120">Чтобы определить, нужно ли запечатывать класс, метод или свойство, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="e94b6-120">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="e94b6-121">потенциальные преимущества, которые производные классы могут получить от возможности настраивать ваш класс;</span><span class="sxs-lookup"><span data-stu-id="e94b6-121">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="e94b6-122">вероятность того, что производные классы могут корректировать ваши классы, препятствуя их нормальной работе.</span><span class="sxs-lookup"><span data-stu-id="e94b6-122">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94b6-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e94b6-123">See Also</span></span>  
 [<span data-ttu-id="e94b6-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e94b6-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e94b6-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e94b6-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e94b6-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e94b6-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e94b6-127">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="e94b6-127">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="e94b6-128">Абстрактные и запечатанные классы и члены классов</span><span class="sxs-lookup"><span data-stu-id="e94b6-128">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="e94b6-129">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="e94b6-129">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="e94b6-130">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="e94b6-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="e94b6-131">override</span><span class="sxs-lookup"><span data-stu-id="e94b6-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="e94b6-132">virtual</span><span class="sxs-lookup"><span data-stu-id="e94b6-132">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)
