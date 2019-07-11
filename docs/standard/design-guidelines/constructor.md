---
title: Разработка конструктора
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: 074aa391b71257584a01171e95da7472354cdc2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746777"
---
# <a name="constructor-design"></a><span data-ttu-id="d9093-102">Разработка конструктора</span><span class="sxs-lookup"><span data-stu-id="d9093-102">Constructor Design</span></span>
<span data-ttu-id="d9093-103">Существует два типа конструкторов: Введите конструкторы и конструкторы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d9093-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="d9093-104">Конструкторы типов являются статическими и выполняются средой CLR, прежде чем использовать тип.</span><span class="sxs-lookup"><span data-stu-id="d9093-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="d9093-105">Конструкторы экземпляров запускаемых при создании экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="d9093-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="d9093-106">Конструкторы типов не могут принимать любые параметры.</span><span class="sxs-lookup"><span data-stu-id="d9093-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="d9093-107">Конструкторы экземпляров можно.</span><span class="sxs-lookup"><span data-stu-id="d9093-107">Instance constructors can.</span></span> <span data-ttu-id="d9093-108">Конструкторы экземпляров, которые не принимают никаких параметров, часто называются конструкторы без параметров.</span><span class="sxs-lookup"><span data-stu-id="d9093-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>  
  
 <span data-ttu-id="d9093-109">Конструкторы — это наиболее удобный способ создания экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="d9093-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="d9093-110">Большинство разработчиков будет поиска и попробуйте использовать конструктор, прежде чем они подумать о других способах создания экземпляров (например, фабричные методы).</span><span class="sxs-lookup"><span data-stu-id="d9093-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="d9093-111">**✓ CONSIDER** предоставляет простой, в идеальном случае по умолчанию, конструкторы.</span><span class="sxs-lookup"><span data-stu-id="d9093-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="d9093-112">Простой конструктор имеет очень небольшое количество параметров, и все параметры являются примитивами или перечисления.</span><span class="sxs-lookup"><span data-stu-id="d9093-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="d9093-113">Такой простой конструкторы повысить удобство использования, платформы.</span><span class="sxs-lookup"><span data-stu-id="d9093-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="d9093-114">**✓ CONSIDER** вместо статический фабричный метод конструктора, если семантика требуемой операции не сопоставляются непосредственно конструкцию нового экземпляра или следующие рекомендации по разработке конструктора неприменимыми.</span><span class="sxs-lookup"><span data-stu-id="d9093-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="d9093-115">**✓ DO** используйте параметры конструкторов как ярлыки для установки значений основных свойств.</span><span class="sxs-lookup"><span data-stu-id="d9093-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="d9093-116">Нет разницы в семантике между следует с помощью пустого конструктора, следуют некоторые наборы свойств и конструктор с несколькими аргументами.</span><span class="sxs-lookup"><span data-stu-id="d9093-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="d9093-117">**✓ DO** использовать то же имя для параметров конструктора и свойства, если параметры конструктора используются только для установки свойства.</span><span class="sxs-lookup"><span data-stu-id="d9093-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="d9093-118">Единственное различие между таких параметров и свойств должны регистр.</span><span class="sxs-lookup"><span data-stu-id="d9093-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="d9093-119">**✓ DO** минимальных затрат в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="d9093-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="d9093-120">Конструктор не должен делать параметры конструктора объем работы, отличных от записи.</span><span class="sxs-lookup"><span data-stu-id="d9093-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="d9093-121">Затраты на любые обработки должен быть задержан, только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d9093-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="d9093-122">**✓ DO** вызывайте исключения из конструкторов экземпляров, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="d9093-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="d9093-123">**✓ СДЕЛАТЬ** явно объявлять открытый конструктор без параметров в классах, в том случае, если такой конструктор является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d9093-123">**✓ DO** explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="d9093-124">Если вы не объявляется явным образом все конструкторы в типе, многие языки (такие как C#) автоматически добавит открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="d9093-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="d9093-125">(Абстрактные классы получить защищенный конструктор).</span><span class="sxs-lookup"><span data-stu-id="d9093-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="d9093-126">Добавление параметризованный конструктор класса не позволяет компилятору добавления конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="d9093-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="d9093-127">Часто в результате случайного критические изменения.</span><span class="sxs-lookup"><span data-stu-id="d9093-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="d9093-128">**X ИЗБЕГАЙТЕ** явное определение конструкторы без параметров для структур.</span><span class="sxs-lookup"><span data-stu-id="d9093-128">**X AVOID** explicitly defining parameterless constructors on structs.</span></span>  
  
 <span data-ttu-id="d9093-129">Это делает создание массива быстрее, так как если не определен конструктор без параметров, она не должна выполняться на каждый слот в массиве.</span><span class="sxs-lookup"><span data-stu-id="d9093-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="d9093-130">Обратите внимание на то, что большинство компиляторов, включая C#, не разрешают структуры могут иметь конструкторы без параметров по этой причине.</span><span class="sxs-lookup"><span data-stu-id="d9093-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="d9093-131">**X AVOID** вызов виртуальные члены объекта внутри его конструктор.</span><span class="sxs-lookup"><span data-stu-id="d9093-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="d9093-132">Вызов виртуальный член приведет к наиболее производный переопределение, чтобы вызываться, даже если конструктор наиболее производный тип не полностью еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="d9093-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="d9093-133">Конструктор правила типов</span><span class="sxs-lookup"><span data-stu-id="d9093-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="d9093-134">**✓ DO** сделать частным статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="d9093-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="d9093-135">Статический конструктор, также известный как конструктор класса используется для инициализации типа.</span><span class="sxs-lookup"><span data-stu-id="d9093-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="d9093-136">Среда CLR вызывает статический конструктор перед созданием первого экземпляра типа или вызываются все статические члены этого типа.</span><span class="sxs-lookup"><span data-stu-id="d9093-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="d9093-137">Пользователь имеет не контролирует, когда вызывается статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="d9093-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="d9093-138">Если статический конструктор не является закрытым, может быть вызвана код, отличный от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d9093-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="d9093-139">В зависимости от операций, выполняемых в конструкторе это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="d9093-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="d9093-140">Компилятор C# вызывает статические конструкторы частной.</span><span class="sxs-lookup"><span data-stu-id="d9093-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="d9093-141">**X DO NOT** вызывайте исключения из статических конструкторов.</span><span class="sxs-lookup"><span data-stu-id="d9093-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="d9093-142">Если исключение создается конструктор типа, тип не может использоваться в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="d9093-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="d9093-143">**✓ CONSIDER** Инициализация встроенного статических полей, а не явно с использованием статических конструкторов, так как среда выполнения может оптимизировать производительность типов, которые не являются явно определенного статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="d9093-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="d9093-144">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d9093-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d9093-145">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d9093-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9093-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d9093-146">See also</span></span>

- [<span data-ttu-id="d9093-147">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="d9093-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="d9093-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="d9093-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
