---
title: virtual (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dce3333646bca6f558e3760849b6cffdb34a6c0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-c-reference"></a><span data-ttu-id="4e71f-102">virtual (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4e71f-102">virtual (C# Reference)</span></span>
<span data-ttu-id="4e71f-103">Ключевое слово `virtual` используется для изменения объявлений методов, свойств, индексаторов и событий и разрешения их переопределения в производном классе.</span><span class="sxs-lookup"><span data-stu-id="4e71f-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="4e71f-104">Например, этот метод может быть переопределен любым наследующим его классом:</span><span class="sxs-lookup"><span data-stu-id="4e71f-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="4e71f-105">Реализацию виртуального члена можно изменить путем [переопределения члена](../../../csharp/language-reference/keywords/override.md) в производном классе.</span><span class="sxs-lookup"><span data-stu-id="4e71f-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="4e71f-106">Дополнительные сведения об использовании ключевого слова `virtual` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="4e71f-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e71f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e71f-107">Remarks</span></span>  
 <span data-ttu-id="4e71f-108">При вызове виртуального метода тип времени выполнения объекта проверяется на переопределение члена.</span><span class="sxs-lookup"><span data-stu-id="4e71f-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="4e71f-109">Вызывается переопределение члена в самом дальнем классе. Это может быть исходный член, если никакой производный класс не выполнял переопределение этого члена.</span><span class="sxs-lookup"><span data-stu-id="4e71f-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="4e71f-110">По умолчанию методы не являются виртуальными.</span><span class="sxs-lookup"><span data-stu-id="4e71f-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="4e71f-111">Такой метод переопределить невозможно.</span><span class="sxs-lookup"><span data-stu-id="4e71f-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="4e71f-112">Нельзя использовать модификатор `virtual` с модификаторами `static`, `abstract`, `private`, или `override`.</span><span class="sxs-lookup"><span data-stu-id="4e71f-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="4e71f-113">В следующем примере показано виртуальное свойство.</span><span class="sxs-lookup"><span data-stu-id="4e71f-113">The following example shows a virtual property:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 <span data-ttu-id="4e71f-114">Действие виртуальных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.</span><span class="sxs-lookup"><span data-stu-id="4e71f-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="4e71f-115">Использование модификатора `virtual` в статическом свойстве является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="4e71f-115">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="4e71f-116">Виртуальное наследуемое свойство может быть переопределено в производном классе путем включения объявления свойства, которое использует модификатор `override`.</span><span class="sxs-lookup"><span data-stu-id="4e71f-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e71f-117">Пример</span><span class="sxs-lookup"><span data-stu-id="4e71f-117">Example</span></span>  
 <span data-ttu-id="4e71f-118">В этом примере класс `Shape` содержит две координаты `x`, `y` и виртуальный метод `Area()`.</span><span class="sxs-lookup"><span data-stu-id="4e71f-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="4e71f-119">Различные классы фигур, такие как `Circle`, `Cylinder` и `Sphere`, наследуют класс `Shape`, и для каждой фигуры вычисляется площадь поверхности.</span><span class="sxs-lookup"><span data-stu-id="4e71f-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="4e71f-120">Каждый производный класс обладает собственной реализацией переопределения метода `Area()`.</span><span class="sxs-lookup"><span data-stu-id="4e71f-120">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="4e71f-121">Обратите внимание, что наследуемые классы `Circle`, `Sphere` и `Cylinder` используют конструкторы, которые инициализируют базовый класс, как показано в следующем объявлении.</span><span class="sxs-lookup"><span data-stu-id="4e71f-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="4e71f-122">Следующая программа вычисляет и отображает соответствующую область для каждой фигуры путем вызова нужной реализации метода `Area()` в соответствии с объектом, связанным с методом.</span><span class="sxs-lookup"><span data-stu-id="4e71f-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4e71f-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4e71f-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e71f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4e71f-124">See Also</span></span>  
 [<span data-ttu-id="4e71f-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4e71f-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4e71f-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4e71f-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4e71f-127">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="4e71f-127">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="4e71f-128">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="4e71f-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4e71f-129">Полиморфизм</span><span class="sxs-lookup"><span data-stu-id="4e71f-129">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="4e71f-130">abstract</span><span class="sxs-lookup"><span data-stu-id="4e71f-130">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="4e71f-131">override</span><span class="sxs-lookup"><span data-stu-id="4e71f-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="4e71f-132">new</span><span class="sxs-lookup"><span data-stu-id="4e71f-132">new</span></span>](../../../csharp/language-reference/keywords/new.md)
