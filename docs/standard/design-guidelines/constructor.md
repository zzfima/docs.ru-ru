---
title: "Разработка конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66a297ed035f5afde06913b89f1f92dee5745f48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="constructor-design"></a><span data-ttu-id="b36df-102">Разработка конструктора</span><span class="sxs-lookup"><span data-stu-id="b36df-102">Constructor Design</span></span>
<span data-ttu-id="b36df-103">Существует два типа конструкторов: конструкторы и конструкторы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b36df-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="b36df-104">Конструкторы типов являются статическими и выполняются средой CLR, прежде чем использовать тип.</span><span class="sxs-lookup"><span data-stu-id="b36df-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="b36df-105">Конструкторы экземпляров выполняются, когда создается экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="b36df-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="b36df-106">Конструкторы типов не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="b36df-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="b36df-107">Конструкторы экземпляров можно.</span><span class="sxs-lookup"><span data-stu-id="b36df-107">Instance constructors can.</span></span> <span data-ttu-id="b36df-108">Конструкторы экземпляров, которые не принимают никаких параметров часто называются конструкторы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b36df-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="b36df-109">Конструкторы являются самым естественным способом создания экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="b36df-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="b36df-110">Большинство разработчиков будет поиска и попробуйте использовать конструктор, прежде чем они подумать о других способах создания экземпляров (например, фабричные методы).</span><span class="sxs-lookup"><span data-stu-id="b36df-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="b36df-111">**✓ Попробуйте** предоставляет простой, в идеальном случае по умолчанию, конструкторы.</span><span class="sxs-lookup"><span data-stu-id="b36df-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="b36df-112">Простой конструктор имеет очень небольшое число параметров, и все параметры являются примитивами или перечисления.</span><span class="sxs-lookup"><span data-stu-id="b36df-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="b36df-113">Такой простой конструкторы повысить удобство использования платформы.</span><span class="sxs-lookup"><span data-stu-id="b36df-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="b36df-114">**✓ Попробуйте** вместо статический фабричный метод конструктора, если семантика требуемой операции не сопоставляются непосредственно конструкцию нового экземпляра или следующие рекомендации по разработке конструктора неприменимыми.</span><span class="sxs-lookup"><span data-stu-id="b36df-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="b36df-115">**✓ СДЕЛАТЬ** используйте параметры конструкторов как ярлыки для установки значений основных свойств.</span><span class="sxs-lookup"><span data-stu-id="b36df-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="b36df-116">Должно быть не семантических различий между с помощью пустого конструктора, следуют некоторые наборы свойств и с помощью конструктора с несколькими аргументами.</span><span class="sxs-lookup"><span data-stu-id="b36df-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="b36df-117">**✓ СДЕЛАТЬ** использовать то же имя для параметров конструктора и свойства, если параметры конструктора используются только для установки свойства.</span><span class="sxs-lookup"><span data-stu-id="b36df-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="b36df-118">Единственное различие между таких параметров и свойств должен регистра.</span><span class="sxs-lookup"><span data-stu-id="b36df-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="b36df-119">**✓ СДЕЛАТЬ** минимальных затрат в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="b36df-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="b36df-120">Конструкторы не следует объем работ, отличных от записи параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="b36df-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="b36df-121">Затраты на какой-либо другой обработки должен быть задержан только по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b36df-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="b36df-122">**✓ СДЕЛАТЬ** вызывайте исключения из конструкторов экземпляров, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="b36df-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="b36df-123">**✓ СДЕЛАТЬ** явно объявить открытый конструктор по умолчанию в классах, если такой конструктор является обязательным.</span><span class="sxs-lookup"><span data-stu-id="b36df-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="b36df-124">Если явно не объявлен каких-либо конструкторов типа, многие языки (например, C#) автоматически добавит открытый конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b36df-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="b36df-125">(Абстрактные классы получить защищенного конструктора).</span><span class="sxs-lookup"><span data-stu-id="b36df-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="b36df-126">Добавление параметризованного конструктора класса указывает компилятору добавить конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b36df-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="b36df-127">Часто в результате случайного критических изменений.</span><span class="sxs-lookup"><span data-stu-id="b36df-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="b36df-128">**X ИЗБЕГАЙТЕ** явное объявление конструкторы по умолчанию для структуры.</span><span class="sxs-lookup"><span data-stu-id="b36df-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="b36df-129">Это делает при создании массива быстрее, поскольку если конструктор по умолчанию не определен, он не имеет для выполнения на каждый слота в массиве.</span><span class="sxs-lookup"><span data-stu-id="b36df-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="b36df-130">Обратите внимание, что большинство компиляторов, включая C# не разрешать структуры могут иметь конструкторы без параметров, по этой причине.</span><span class="sxs-lookup"><span data-stu-id="b36df-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="b36df-131">**X ИЗБЕГАЙТЕ** вызов виртуальные члены объекта внутри его конструктор.</span><span class="sxs-lookup"><span data-stu-id="b36df-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="b36df-132">Вызов виртуальный член будет вызвать наибольшие производные переопределения для вызова, даже если конструктор наиболее производный тип не полностью еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="b36df-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="b36df-133">Правила конструктора типов</span><span class="sxs-lookup"><span data-stu-id="b36df-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="b36df-134">**✓ СДЕЛАТЬ** сделать частным статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="b36df-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="b36df-135">Статический конструктор, также называемый конструктором класса, используется для инициализации типа.</span><span class="sxs-lookup"><span data-stu-id="b36df-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="b36df-136">Среда CLR вызывает статический конструктор перед созданием первого экземпляра типа или вызываются любые статические члены этого типа.</span><span class="sxs-lookup"><span data-stu-id="b36df-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="b36df-137">Пользователь не обеспечивает контроль за при вызове статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="b36df-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="b36df-138">Если статический конструктор не является закрытым, он может быть вызван код, отличный от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b36df-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="b36df-139">В зависимости от операций, выполняемых в конструкторе это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="b36df-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="b36df-140">Компилятор C# вызывает статические конструкторы должно быть закрытым.</span><span class="sxs-lookup"><span data-stu-id="b36df-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="b36df-141">**X не** вызывайте исключения из статических конструкторов.</span><span class="sxs-lookup"><span data-stu-id="b36df-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="b36df-142">Если исключение вызывается из конструктора типа, тип не может использоваться в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b36df-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="b36df-143">**✓ Попробуйте** Инициализация встроенного статических полей, а не явно с использованием статических конструкторов, так как среда выполнения может оптимизировать производительность типов, которые не являются явно определенного статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="b36df-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="b36df-144">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="b36df-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b36df-145">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b36df-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36df-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b36df-146">See Also</span></span>  
 [<span data-ttu-id="b36df-147">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="b36df-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="b36df-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="b36df-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
