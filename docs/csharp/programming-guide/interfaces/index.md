---
title: "Интерфейсы (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
caps.latest.revision: 45
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
ms.openlocfilehash: 0552cea71f66ba8c299b1706cab6778c9e3367c9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="interfaces-c-programming-guide"></a><span data-ttu-id="bb9f2-102">Интерфейсы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="bb9f2-102">Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="bb9f2-103">Интерфейс содержит определения для группы связанных функциональных возможностей, которые может реализовать [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-103">An interface contains definitions for a group of related functionalities that a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md) can implement.</span></span>  
  
 <span data-ttu-id="bb9f2-104">С помощью интерфейсов можно, например, включить в класс поведение из нескольких источников.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-104">By using interfaces, you can, for example, include behavior from multiple sources in a class.</span></span> <span data-ttu-id="bb9f2-105">Эта возможность очень важна в C#, поскольку этот язык не поддерживает множественное наследование классов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-105">That capability is important in C# because the language doesn't support multiple inheritance of classes.</span></span> <span data-ttu-id="bb9f2-106">Кроме того, необходимо использовать интерфейс, если требуется имитировать наследование для структур, поскольку они не могут фактически наследовать от другой структуры или класса.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-106">In addition, you must use an interface if you want to simulate inheritance for structs, because they can't actually inherit from another struct or class.</span></span>  
  
 <span data-ttu-id="bb9f2-107">Интерфейс определяется с помощью ключевого слова [interface](../../../csharp/language-reference/keywords/interface.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-107">You define an interface by using the [interface](../../../csharp/language-reference/keywords/interface.md) keyword, as the following example shows.</span></span>  
  
 <span data-ttu-id="bb9f2-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb9f2-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="bb9f2-109">Любой объект (класс или структура), реализующий интерфейс <xref:System.IEquatable%601>, должен содержать определение для метода <xref:System.IEquatable%601.Equals%2A>, соответствующее сигнатуре, которую задает интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-109">Any class or struct that implements the <xref:System.IEquatable%601> interface must contain a definition for an <xref:System.IEquatable%601.Equals%2A> method that matches the signature that the interface specifies.</span></span> <span data-ttu-id="bb9f2-110">В результате вы можете быть уверены, что класс, реализующий `IEquatable<T>`, содержит метод `Equals`, с помощью которого экземпляр этого класса может определить, равен ли он другому экземпляру того же класса.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-110">As a result, you can count on a class that implements `IEquatable<T>` to contain an `Equals` method with which an instance of the class can determine whether it's equal to another instance of the same class.</span></span>  
  
 <span data-ttu-id="bb9f2-111">Определение `IEquatable<T>` не предоставляет реализацию для метода `Equals`.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-111">The definition of `IEquatable<T>` doesn’t provide an implementation for `Equals`.</span></span> <span data-ttu-id="bb9f2-112">Интерфейс определяет только сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-112">The interface defines only the signature.</span></span> <span data-ttu-id="bb9f2-113">Таким образом, интерфейс в C# аналогичен абстрактному классу, в котором все методы являются абстрактными.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-113">In that way, an interface in C# is similar to an abstract class in which all the methods are abstract.</span></span> <span data-ttu-id="bb9f2-114">Класс или структура может реализовывать несколько интерфейсов, но класс может наследовать только одному классу, абстрактному или нет.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-114">However, a class or struct can implement multiple interfaces, but a class can inherit only a single class, abstract or not.</span></span> <span data-ttu-id="bb9f2-115">Таким образом, с помощью интерфейсов можно включить в класс поведение из нескольких источников.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-115">Therefore, by using interfaces, you can include behavior from multiple sources in a class.</span></span>  
  
 <span data-ttu-id="bb9f2-116">Дополнительные сведения об абстрактных классах см. в статье [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) (Абстрактные и запечатанные классы и члены классов).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-116">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="bb9f2-117">Интерфейсы могут содержать методы, свойства, события, индексаторы, а также любое сочетание этих четырех типов членов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-117">Interfaces can contain methods, properties, events, indexers, or any combination of those four member types.</span></span> <span data-ttu-id="bb9f2-118">Ссылки на примеры см. в разделе [Связанные разделы](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-118">For links to examples, see [Related Sections](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span></span> <span data-ttu-id="bb9f2-119">Интерфейс не может содержать константы, поля, операторы, конструкторы экземпляров, методы завершения или типы.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-119">An interface can't contain constants, fields, operators, instance constructors, finalizers, or types.</span></span> <span data-ttu-id="bb9f2-120">Члены интерфейса автоматически являются открытыми, и они не могут включать модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-120">Interface members are automatically public, and they can't include any access modifiers.</span></span> <span data-ttu-id="bb9f2-121">Члены также не могут быть [статическими](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-121">Members also can't be [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
 <span data-ttu-id="bb9f2-122">Для реализации члена интерфейса соответствующий член реализующего класса должен быть открытым и не статическим, а также иметь такое же имя и сигнатуру, что и член интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-122">To implement an interface member, the corresponding member of the implementing class must be public, non-static, and have the same name and signature as the interface member.</span></span>  
  
 <span data-ttu-id="bb9f2-123">Если класс (или структура) реализует интерфейс, этот класс (или структура) должен предоставлять реализацию для всех членов, которые определяет этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-123">When a class or struct implements an interface, the class or struct must provide an implementation for all of the members that the interface defines.</span></span> <span data-ttu-id="bb9f2-124">Сам интерфейс не предоставляет функциональность, которую класс или структура может наследовать таким же образом, как можно наследовать функциональность базового класса.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-124">The interface itself provides no functionality that a class or struct can inherit in the way that it can inherit base class functionality.</span></span> <span data-ttu-id="bb9f2-125">Однако если базовый класс реализует интерфейс, то любой класс, производный от базового класса, наследует эту реализацию.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-125">However, if a base class implements an interface, any class that's derived from the base class inherits that implementation.</span></span>  
  
 <span data-ttu-id="bb9f2-126">В следующем примере показана реализация интерфейса IEquatable<T\>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-126">The following example shows an implementation of the IEquatable<T\> interface.</span></span> <span data-ttu-id="bb9f2-127">Реализующий класс `Car` должен предоставлять реализацию метода <xref:System.IEquatable%601.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-127">The implementing class, `Car`, must provide an implementation of the <xref:System.IEquatable%601.Equals%2A> method.</span></span>  
  
 <span data-ttu-id="bb9f2-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb9f2-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="bb9f2-129">Свойства и индексаторы класса могут определять дополнительные методы доступа для свойства или индексатора, определенного в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-129">Properties and indexers of a class can define extra accessors for a property or indexer that's defined in an interface.</span></span> <span data-ttu-id="bb9f2-130">Например, интерфейс может объявлять свойство, имеющее акцессор [get](../../../csharp/language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-130">For example, an interface might declare a property that has a [get](../../../csharp/language-reference/keywords/get.md) accessor.</span></span> <span data-ttu-id="bb9f2-131">Класс, реализующий этот интерфейс, может объявлять это же свойство с обоими акцессорами (`get` и [set](../../../csharp/language-reference/keywords/set.md)).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-131">The class that implements the interface can declare the same property with both a `get` and [set](../../../csharp/language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="bb9f2-132">Однако если свойство или индексатор использует явную реализацию, методы доступа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-132">However, if the property or indexer uses explicit implementation, the accessors must match.</span></span> <span data-ttu-id="bb9f2-133">Дополнительные сведения о явной реализации см. в статьях [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) и [Свойства интерфейса](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-133">For more information about explicit implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) and [Interface Properties](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span></span>  
  
 <span data-ttu-id="bb9f2-134">Интерфейсы могут реализовывать другие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-134">Interfaces can implement other interfaces.</span></span> <span data-ttu-id="bb9f2-135">Класс может включать интерфейс несколько раз через базовые классы, которым он наследует, или через интерфейсы, которые реализуют другие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-135">A class might include an interface multiple times through base classes that it inherits or through interfaces that other interfaces implement.</span></span> <span data-ttu-id="bb9f2-136">Однако класс может предоставить реализацию интерфейса только однократно и только если класс объявляет интерфейс как часть определения класса (`class ClassName : InterfaceName`).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-136">However, the class can provide an implementation of an interface only one time and only if the class declares the interface as part of the definition of the class (`class ClassName : InterfaceName`).</span></span> <span data-ttu-id="bb9f2-137">Если интерфейс наследуется, поскольку наследуется базовый класс, реализующий этот интерфейс, то базовый класс предоставляет реализацию членов этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-137">If the interface is inherited because you inherited a base class that implements the interface, the base class provides the implementation of the members of the interface.</span></span> <span data-ttu-id="bb9f2-138">Однако производный класс может повторно реализовать члены интерфейса вместо использования унаследованной реализации.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-138">However, the derived class can reimplement the interface members instead of using the inherited implementation.</span></span>  
  
 <span data-ttu-id="bb9f2-139">Базовый класс также может реализовывать члены интерфейса с помощью виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-139">A base class can also implement interface members by using virtual members.</span></span> <span data-ttu-id="bb9f2-140">В таком случае производный класс может изменять поведение интерфейса путем переопределения виртуальных членов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-140">In that case, a derived class can change the interface behavior by overriding the virtual members.</span></span> <span data-ttu-id="bb9f2-141">Дополнительные сведения о виртуальных членах см. в статье [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="bb9f2-141">For more information about virtual members, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="interfaces-summary"></a><span data-ttu-id="bb9f2-142">Сводные сведения по интерфейсам</span><span class="sxs-lookup"><span data-stu-id="bb9f2-142">Interfaces Summary</span></span>  
 <span data-ttu-id="bb9f2-143">Интерфейс имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-143">An interface has the following properties:</span></span>  
  
-   <span data-ttu-id="bb9f2-144">Интерфейс подобен абстрактному базовому классу.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-144">An interface is like an abstract base class.</span></span> <span data-ttu-id="bb9f2-145">Любой класс (или структура), реализующий интерфейс, должен реализовывать все его члены.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-145">Any class or struct that implements the interface must implement all its members.</span></span>  
  
-   <span data-ttu-id="bb9f2-146">Невозможно создать экземпляр интерфейса напрямую.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-146">An interface can't be instantiated directly.</span></span> <span data-ttu-id="bb9f2-147">Его члены реализуются любым классом (или структурой), реализующим интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-147">Its members are implemented by any class or struct that implements the interface.</span></span>  
  
-   <span data-ttu-id="bb9f2-148">Интерфейсы могут содержать события, индексаторы, методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-148">Interfaces can contain events, indexers, methods, and properties.</span></span>  
  
-   <span data-ttu-id="bb9f2-149">Интерфейсы не содержат реализацию методов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-149">Interfaces contain no implementation of methods.</span></span>  
  
-   <span data-ttu-id="bb9f2-150">Класс или структура может реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-150">A class or struct can implement multiple interfaces.</span></span> <span data-ttu-id="bb9f2-151">Класс может наследовать базовому классу и также реализовывать один или несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-151">A class can inherit a base class and also implement one or more interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb9f2-152">Содержание</span><span class="sxs-lookup"><span data-stu-id="bb9f2-152">In This Section</span></span>  
 [<span data-ttu-id="bb9f2-153">Явная реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb9f2-153">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 <span data-ttu-id="bb9f2-154">В этом разделе объясняется, как создать член класса, который относится к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-154">Explains how to create a class member that’s specific to an interface.</span></span>  
  
 [<span data-ttu-id="bb9f2-155">Практическое руководство. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb9f2-155">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)  
 <span data-ttu-id="bb9f2-156">В этом разделе содержится пример явной реализации членов интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-156">Provides an example of how to explicitly implement members of interfaces.</span></span>  
  
 [<span data-ttu-id="bb9f2-157">Практическое руководство. Явная реализация членов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="bb9f2-157">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)  
 <span data-ttu-id="bb9f2-158">В этом разделе содержится пример явной реализации членов интерфейсов с помощью наследования.</span><span class="sxs-lookup"><span data-stu-id="bb9f2-158">Provides an example of how to explicitly implement members of interfaces with inheritance.</span></span>  
  
##  <span data-ttu-id="bb9f2-159"><a name="BKMK_RelatedSections"></a> Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bb9f2-159"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="bb9f2-160">Свойства интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb9f2-160">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="bb9f2-161">Индексаторы в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="bb9f2-161">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="bb9f2-162">Практическое руководство. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb9f2-162">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="bb9f2-163">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="bb9f2-163">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [<span data-ttu-id="bb9f2-164">Наследование</span><span class="sxs-lookup"><span data-stu-id="bb9f2-164">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
  
-   [<span data-ttu-id="bb9f2-165">Методы</span><span class="sxs-lookup"><span data-stu-id="bb9f2-165">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="bb9f2-166">Полиморфизм</span><span class="sxs-lookup"><span data-stu-id="bb9f2-166">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
  
-   [<span data-ttu-id="bb9f2-167">Абстрактные и запечатанные классы и члены классов</span><span class="sxs-lookup"><span data-stu-id="bb9f2-167">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
  
-   [<span data-ttu-id="bb9f2-168">Свойства</span><span class="sxs-lookup"><span data-stu-id="bb9f2-168">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [<span data-ttu-id="bb9f2-169">События</span><span class="sxs-lookup"><span data-stu-id="bb9f2-169">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
  
-   [<span data-ttu-id="bb9f2-170">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="bb9f2-170">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="bb9f2-171">Важная глава книги</span><span class="sxs-lookup"><span data-stu-id="bb9f2-171">Featured Book Chapter</span></span>  
 <span data-ttu-id="bb9f2-172">Глава [Интерфейсы](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) в документе [Изучение C# 3.0: овладение основными понятиями C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb9f2-172">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9f2-173">См. также</span><span class="sxs-lookup"><span data-stu-id="bb9f2-173">See Also</span></span>  
 <span data-ttu-id="bb9f2-174">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb9f2-174">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bb9f2-175">Наследование</span><span class="sxs-lookup"><span data-stu-id="bb9f2-175">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

