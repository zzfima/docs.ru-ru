---
title: abstract. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: a6c0ac86689c5d095fc077beb39d6281f77aab24
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422944"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="6e029-102">abstract (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6e029-102">abstract (C# Reference)</span></span>
<span data-ttu-id="6e029-103">Модификатор `abstract` указывает, что изменяемый элемент имеет отсутствующую или неполную реализацию.</span><span class="sxs-lookup"><span data-stu-id="6e029-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="6e029-104">Модификатор abstract можно использовать с классами, методами, свойствами, индексаторами и событиями.</span><span class="sxs-lookup"><span data-stu-id="6e029-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="6e029-105">Используйте модификатор `abstract` в объявлении класса, чтобы указать, что класс предназначен только для использования в качестве базового класса для других классов и не должен быть создан сам по себе.</span><span class="sxs-lookup"><span data-stu-id="6e029-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="6e029-106">Элементы с пометкой abstract должны быть реализованы не абстрактными классами, производными от абстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="6e029-106">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="6e029-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6e029-107">Example</span></span>  
 <span data-ttu-id="6e029-108">В этом примере класс `Square` должен обеспечивать реализацию `GetArea`, поскольку является производным от класса `Shape`:</span><span class="sxs-lookup"><span data-stu-id="6e029-108">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="6e029-109">Абстрактные классы предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6e029-109">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="6e029-110">Создавать экземпляры абстрактного класса нельзя.</span><span class="sxs-lookup"><span data-stu-id="6e029-110">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="6e029-111">Абстрактный класс может содержать абстрактные методы и методы доступа.</span><span class="sxs-lookup"><span data-stu-id="6e029-111">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="6e029-112">Изменить абстрактный класс с модификатором [sealed](./sealed.md) нельзя, так как два этих модификатора имеют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="6e029-112">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="6e029-113">Модификатор `sealed` запрещает наследование класса, в то время как модификатор `abstract` указывает, что класс обязан иметь производные классы.</span><span class="sxs-lookup"><span data-stu-id="6e029-113">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="6e029-114">Неабстрактный класс, производный от абстрактного класса, должен включать фактические реализации всех наследуемых абстрактных методов и методов доступа.</span><span class="sxs-lookup"><span data-stu-id="6e029-114">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="6e029-115">Модификатор `abstract` в объявлении метода или свойства позволяет указать, что этот метод или свойство не содержат реализации.</span><span class="sxs-lookup"><span data-stu-id="6e029-115">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="6e029-116">Абстрактные методы предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6e029-116">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="6e029-117">Абстрактный метод неявно представляет собой виртуальный метод.</span><span class="sxs-lookup"><span data-stu-id="6e029-117">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="6e029-118">Объявления абстрактных методов допускаются только в абстрактных классах.</span><span class="sxs-lookup"><span data-stu-id="6e029-118">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="6e029-119">Поскольку объявление абстрактного метода не предоставляет фактической реализации, тело метода отсутствует, а объявление метода заканчивается точкой с запятой, и фигурных скобок ({ }) после подписи нет.</span><span class="sxs-lookup"><span data-stu-id="6e029-119">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="6e029-120">Например:</span><span class="sxs-lookup"><span data-stu-id="6e029-120">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="6e029-121">Реализация предоставляется методом [override](./override.md), который является членом неабстрактного класса.</span><span class="sxs-lookup"><span data-stu-id="6e029-121">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="6e029-122">В объявлении абстрактного метода нельзя использовать [статические](./static.md) или [виртуальные](./virtual.md) модификаторы.</span><span class="sxs-lookup"><span data-stu-id="6e029-122">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="6e029-123">Действие абстрактных свойств аналогично абстрактным методам, за исключением отличий в синтаксисе объявлений и вызовов.</span><span class="sxs-lookup"><span data-stu-id="6e029-123">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="6e029-124">Использование модификатора `abstract` в статическом свойстве является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="6e029-124">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="6e029-125">Абстрактное наследуемое свойство можно переопределить в производном классе, включив объявление свойства, которое использует модификатор [override](./override.md).</span><span class="sxs-lookup"><span data-stu-id="6e029-125">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="6e029-126">Дополнительные сведения об абстрактных классах см. в разделе [Абстрактные и запечатанные классы и члены классов](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="6e029-126">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="6e029-127">Абстрактный класс должен предоставлять реализацию для всех членов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6e029-127">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="6e029-128">Абстрактный класс, реализующий интерфейс, может сопоставлять методы интерфейса с абстрактными методами.</span><span class="sxs-lookup"><span data-stu-id="6e029-128">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="6e029-129">Например:</span><span class="sxs-lookup"><span data-stu-id="6e029-129">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="6e029-130">Пример</span><span class="sxs-lookup"><span data-stu-id="6e029-130">Example</span></span>  
 <span data-ttu-id="6e029-131">В следующем примере класс `DerivedClass` является производным от абстрактного класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="6e029-131">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="6e029-132">Абстрактный класс содержит абстрактный метод, `AbstractMethod`, и два абстрактных свойства, `X` и `Y`.</span><span class="sxs-lookup"><span data-stu-id="6e029-132">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="6e029-133">В предыдущем примере при попытке создать экземпляр абстрактного класса с помощью оператора вида:</span><span class="sxs-lookup"><span data-stu-id="6e029-133">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="6e029-134">Выдается сообщение об ошибке, указывающее, что компилятор не может создать экземпляр абстрактного класса BaseClass.</span><span class="sxs-lookup"><span data-stu-id="6e029-134">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6e029-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6e029-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e029-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6e029-136">See also</span></span>

- [<span data-ttu-id="6e029-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6e029-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e029-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6e029-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6e029-139">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="6e029-139">Modifiers</span></span>](index.md)
- [<span data-ttu-id="6e029-140">virtual</span><span class="sxs-lookup"><span data-stu-id="6e029-140">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="6e029-141">override</span><span class="sxs-lookup"><span data-stu-id="6e029-141">override</span></span>](./override.md)
- [<span data-ttu-id="6e029-142">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6e029-142">C# Keywords</span></span>](./index.md)
