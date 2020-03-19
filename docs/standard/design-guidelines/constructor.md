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
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401247"
---
# <a name="constructor-design"></a><span data-ttu-id="ce454-102">Разработка конструктора</span><span class="sxs-lookup"><span data-stu-id="ce454-102">Constructor Design</span></span>

<span data-ttu-id="ce454-103">Есть два вида конструкторов: тип конструкторов и экземпляр конструкторов.</span><span class="sxs-lookup"><span data-stu-id="ce454-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="ce454-104">Конструкторы типа статичны и управляются CLR до использования типа.</span><span class="sxs-lookup"><span data-stu-id="ce454-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="ce454-105">Конструкторы экземпляров работают при создании экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="ce454-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="ce454-106">Конструкторы типа не могут принимать какие-либо параметры.</span><span class="sxs-lookup"><span data-stu-id="ce454-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="ce454-107">Инстанции конструкторы могут.</span><span class="sxs-lookup"><span data-stu-id="ce454-107">Instance constructors can.</span></span> <span data-ttu-id="ce454-108">Конструкторы экземпляров, которые не принимают никаких параметров, часто называют беспараметрыными конструкторами.</span><span class="sxs-lookup"><span data-stu-id="ce454-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="ce454-109">Конструкторы являются наиболее естественным способом создания экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="ce454-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="ce454-110">Большинство разработчиков будут искать и пытаться использовать конструктор, прежде чем они рассматривают альтернативные способы создания экземпляров (например, заводские методы).</span><span class="sxs-lookup"><span data-stu-id="ce454-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="ce454-111">✔️ CONSIDER, предоставляя простые, идеально по умолчанию, конструкторы.</span><span class="sxs-lookup"><span data-stu-id="ce454-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="ce454-112">Простой конструктор имеет очень небольшое количество параметров, и все параметры примитивы или перечисления.</span><span class="sxs-lookup"><span data-stu-id="ce454-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="ce454-113">Такие простые конструкторы повышают удобство использования каркаса.</span><span class="sxs-lookup"><span data-stu-id="ce454-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="ce454-114">✔️ CONSIDER с помощью статического фабричного метода вместо конструктора, если семантика желаемой операции не отображает непосредственно конструкцию нового экземпляра, или если следовать руководящим принципам проектирования конструктора кажется неестественным.</span><span class="sxs-lookup"><span data-stu-id="ce454-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="ce454-115">✔️ DO используют параметры конструктора в качестве ярлыков для настройки основных свойств.</span><span class="sxs-lookup"><span data-stu-id="ce454-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="ce454-116">Не должно быть никакой разницы в семантике между использованием пустого конструктора, за которым следуют некоторые наборы свойств, и использованием конструктора с несколькими аргументами.</span><span class="sxs-lookup"><span data-stu-id="ce454-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="ce454-117">✔️ do использовать одно и то же имя для параметров конструктора и свойство, если параметры конструктора используются для простого набора свойства.</span><span class="sxs-lookup"><span data-stu-id="ce454-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="ce454-118">Единственное различие между такими параметрами и свойствами должно быть оболочкой.</span><span class="sxs-lookup"><span data-stu-id="ce454-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="ce454-119">✔️ сделать минимальную работу в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ce454-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="ce454-120">Конструкторы не должны делать много работы, кроме захвата параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="ce454-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="ce454-121">Стоимость любой другой обработки должна быть отложена до тех пор, пока требуется.</span><span class="sxs-lookup"><span data-stu-id="ce454-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="ce454-122">✔️, если это необходимо, выбрасывает исключения из конструкторов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ce454-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="ce454-123">✔️ совершенно прямо объявить общественный безпараметр конструкции в классах, если такой конструктор не требуется.</span><span class="sxs-lookup"><span data-stu-id="ce454-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="ce454-124">Если вы явно не объявите о каких-либо конструкторах по типу, многие языки (например, C) автоматически добавят непосильным параметрам.</span><span class="sxs-lookup"><span data-stu-id="ce454-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="ce454-125">(Абстрактные классы получают защищенный конструктор.)</span><span class="sxs-lookup"><span data-stu-id="ce454-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="ce454-126">Добавление параметризированного конструктора в класс не позволяет компилятору добавлять безпараметр.</span><span class="sxs-lookup"><span data-stu-id="ce454-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="ce454-127">Это часто приводит к случайным изменениям нарушения.</span><span class="sxs-lookup"><span data-stu-id="ce454-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="ce454-128">❌AVOID явно определяет беспараметрыные конструкторы на структурах.</span><span class="sxs-lookup"><span data-stu-id="ce454-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="ce454-129">Это ускоряет создание массива, потому что если конструктор без параметров не определен, он не должен быть запущен на каждом слоте в массиве.</span><span class="sxs-lookup"><span data-stu-id="ce454-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="ce454-130">Обратите внимание, что многие компиляторы, в том числе C, не позволяют структураторам иметь беспараметрыные конструкторы по этой причине.</span><span class="sxs-lookup"><span data-stu-id="ce454-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="ce454-131">❌AVOID вызывает виртуальных членов на объект внутри своего конструктора.</span><span class="sxs-lookup"><span data-stu-id="ce454-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="ce454-132">Вызов виртуального участника вызовет наиболее производный переопределение, даже если конструктор наиболее производного типа еще не был полностью запущен.</span><span class="sxs-lookup"><span data-stu-id="ce454-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="ce454-133">Руководящие принципы ввода-конструктора</span><span class="sxs-lookup"><span data-stu-id="ce454-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="ce454-134">✔️ сделать статические конструкторы частными.</span><span class="sxs-lookup"><span data-stu-id="ce454-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="ce454-135">Для инициализации типа используется статический конструктор, также называемый конструктором класса.</span><span class="sxs-lookup"><span data-stu-id="ce454-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="ce454-136">CLR вызывает статический конструктор до создания первого экземпляра типа или вызова каких-либо статических членов этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce454-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="ce454-137">Пользователь не может контролировать, когда называется статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="ce454-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="ce454-138">Если статический конструктор не является закрытым, его можно назвать кодом, кроме CLR.</span><span class="sxs-lookup"><span data-stu-id="ce454-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="ce454-139">В зависимости от операций, выполняемых в конструкторе, это может привести к неожиданному поведению.</span><span class="sxs-lookup"><span data-stu-id="ce454-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="ce454-140">Компилятор C' заставляет статических конструкторов быть частными.</span><span class="sxs-lookup"><span data-stu-id="ce454-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="ce454-141">❌НЕ выбрасывайте исключения из статических конструкторов.</span><span class="sxs-lookup"><span data-stu-id="ce454-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="ce454-142">Если исключение выбрасывается из конструктора типа, тип не используется в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="ce454-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="ce454-143">✔️ CONSIDER инициализации статические поля встроенной, а не явно с помощью статических конструкторов, потому что время выполнения способно оптимизировать производительность типов, которые не имеют четко определенного статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="ce454-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="ce454-144">*Порции © 2005, 2009 Microsoft Corporation. Все права зарезервированы.*</span><span class="sxs-lookup"><span data-stu-id="ce454-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="ce454-145">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ce454-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ce454-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce454-146">See also</span></span>

- [<span data-ttu-id="ce454-147">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="ce454-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="ce454-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="ce454-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
