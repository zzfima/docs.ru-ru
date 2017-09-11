---
title: "abstract (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
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
ms.openlocfilehash: a109a8e37f84a2e91229bfce789a69cdc26adba9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-c-reference"></a><span data-ttu-id="6d8a7-102">abstract (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6d8a7-102">abstract (C# Reference)</span></span>
<span data-ttu-id="6d8a7-103">Модификатор `abstract` указывает, что изменяемый элемент имеет отсутствующую или неполную реализацию.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="6d8a7-104">Модификатор abstract можно использовать с классами, методами, свойствами, индексаторами и событиями.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="6d8a7-105">Модификатор `abstract` в определении класса позволяет указать, что класс может быть только базовым классом для других классов.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes.</span></span> <span data-ttu-id="6d8a7-106">Члены, помеченные как абстрактные или включенные в абстрактный класс, должны быть реализованы классами, производными от абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-106">Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d8a7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6d8a7-107">Example</span></span>  
 <span data-ttu-id="6d8a7-108">В этом примере класс `Square` должен обеспечивать реализацию `Area`, поскольку является производным от класса `ShapesClass`:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-108">In this example, the class `Square` must provide an implementation of `Area` because it derives from `ShapesClass`:</span></span>  
  
 <span data-ttu-id="6d8a7-109">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d8a7-109">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]</span></span>  
  
 <span data-ttu-id="6d8a7-110">Абстрактные классы предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-110">Abstract classes have the following features:</span></span>  
  
-   <span data-ttu-id="6d8a7-111">Создавать экземпляры абстрактного класса нельзя.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-111">An abstract class cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="6d8a7-112">Абстрактный класс может содержать абстрактные методы и методы доступа.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
-   <span data-ttu-id="6d8a7-113">Изменить абстрактный класс с модификатором [sealed](../../../csharp/language-reference/keywords/sealed.md) нельзя, поскольку два этих модификатора имеют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-113">It is not possible to modify an abstract class with the [sealed](../../../csharp/language-reference/keywords/sealed.md) modifier because the two modifers have opposite meanings.</span></span> <span data-ttu-id="6d8a7-114">Модификатор `sealed` запрещает наследование класса, в то время как модификатор `abstract` указывает, что класс обязан иметь производные классы.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
-   <span data-ttu-id="6d8a7-115">Неабстрактный класс, производный от абстрактного класса, должен включать фактические реализации всех наследуемых абстрактных методов и методов доступа.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="6d8a7-116">Модификатор `abstract` в объявлении метода или свойства позволяет указать, что этот метод или свойство не содержат реализации.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="6d8a7-117">Абстрактные методы предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-117">Abstract methods have the following features:</span></span>  
  
-   <span data-ttu-id="6d8a7-118">Абстрактный метод неявно представляет собой виртуальный метод.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-118">An abstract method is implicitly a virtual method.</span></span>  
  
-   <span data-ttu-id="6d8a7-119">Объявления абстрактных методов допускаются только в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
-   <span data-ttu-id="6d8a7-120">Поскольку объявление абстрактного метода не предоставляет фактической реализации, тело метода отсутствует, а объявление метода заканчивается точкой с запятой, и фигурных скобок ({ }) после подписи нет.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="6d8a7-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-121">For example:</span></span>  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="6d8a7-122">Реализация предоставляется методом переопределения [override](../../../csharp/language-reference/keywords/override.md), который является членом неабстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-122">The implementation is provided by an overriding method[override](../../../csharp/language-reference/keywords/override.md), which is a member of a non-abstract class.</span></span>  
  
-   <span data-ttu-id="6d8a7-123">В объявлении абстрактного метода нельзя использовать [статические](../../../csharp/language-reference/keywords/static.md) или [виртуальные](../../../csharp/language-reference/keywords/virtual.md) модификаторы.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-123">It is an error to use the [static](../../../csharp/language-reference/keywords/static.md) or [virtual](../../../csharp/language-reference/keywords/virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="6d8a7-124">Действие абстрактных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="6d8a7-125">Использование модификатора `abstract` в статическом свойстве является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="6d8a7-126">Абстрактное наследуемое свойство можно переопределить в производном классе, включив объявление свойства, которое использует модификатор [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="6d8a7-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](../../../csharp/language-reference/keywords/override.md) modifier.</span></span>  
  
 <span data-ttu-id="6d8a7-127">Дополнительные сведения об абстрактных классах см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="6d8a7-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="6d8a7-128">Абстрактный класс должен предоставлять реализацию для всех членов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="6d8a7-129">Абстрактный класс, реализующий интерфейс, может сопоставлять методы интерфейса с абстрактными методами.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="6d8a7-130">Например:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-130">For example:</span></span>  
  
 <span data-ttu-id="6d8a7-131">[!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d8a7-131">[!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d8a7-132">Пример</span><span class="sxs-lookup"><span data-stu-id="6d8a7-132">Example</span></span>  
 <span data-ttu-id="6d8a7-133">В следующем примере класс `DerivedClass` является производным от абстрактного класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-133">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="6d8a7-134">Абстрактный класс содержит абстрактный метод, `AbstractMethod`, и два абстрактных свойства, `X` и `Y`.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-134">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
 <span data-ttu-id="6d8a7-135">[!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d8a7-135">[!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]</span></span>  
  
 <span data-ttu-id="6d8a7-136">В предыдущем примере при попытке создать экземпляр абстрактного класса с помощью оператора вида:</span><span class="sxs-lookup"><span data-stu-id="6d8a7-136">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 <span data-ttu-id="6d8a7-137">выдается сообщение об ошибке, указывающее, что компилятор не может создать экземпляр абстрактного класса BaseClass.</span><span class="sxs-lookup"><span data-stu-id="6d8a7-137">you will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d8a7-138">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6d8a7-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d8a7-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6d8a7-139">See Also</span></span>  
 <span data-ttu-id="6d8a7-140">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d8a7-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6d8a7-141">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d8a7-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6d8a7-142">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="6d8a7-142">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="6d8a7-143">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="6d8a7-143">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="6d8a7-144">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="6d8a7-144">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="6d8a7-145">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6d8a7-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

