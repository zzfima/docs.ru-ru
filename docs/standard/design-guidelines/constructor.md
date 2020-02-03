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
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741733"
---
# <a name="constructor-design"></a><span data-ttu-id="75d48-102">Разработка конструктора</span><span class="sxs-lookup"><span data-stu-id="75d48-102">Constructor Design</span></span>

<span data-ttu-id="75d48-103">Существует два вида конструкторов: конструкторы типов и конструкторы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="75d48-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="75d48-104">Конструкторы типов являются статическими и выполняются средой CLR перед использованием типа.</span><span class="sxs-lookup"><span data-stu-id="75d48-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="75d48-105">Конструкторы экземпляров запускаются при создании экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="75d48-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="75d48-106">Конструкторы типов не могут принимать параметры.</span><span class="sxs-lookup"><span data-stu-id="75d48-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="75d48-107">Конструкторы экземпляров могут.</span><span class="sxs-lookup"><span data-stu-id="75d48-107">Instance constructors can.</span></span> <span data-ttu-id="75d48-108">Конструкторы экземпляров, которые не принимают параметры, часто называются конструкторами без параметров.</span><span class="sxs-lookup"><span data-stu-id="75d48-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="75d48-109">Конструкторы — это наиболее естественный способ создания экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="75d48-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="75d48-110">Большинство разработчиков будут искать и пытаться использовать конструктор, прежде чем они рассчитают альтернативные способы создания экземпляров (например, фабричные методы).</span><span class="sxs-lookup"><span data-stu-id="75d48-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="75d48-111">✔️ Рассмотрите возможность предоставления простых, идеально используемых по умолчанию конструкторов.</span><span class="sxs-lookup"><span data-stu-id="75d48-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="75d48-112">Простой конструктор имеет очень небольшое количество параметров, и все параметры являются примитивами или перечислениями.</span><span class="sxs-lookup"><span data-stu-id="75d48-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="75d48-113">Такие простые конструкторы увеличивают удобство использования платформы.</span><span class="sxs-lookup"><span data-stu-id="75d48-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="75d48-114">✔️ РЕКОМЕНДУЕТСЯ использовать статический фабричный метод вместо конструктора, если семантика требуемой операции не сопоставляется непосредственно с построением нового экземпляра или если следовать рекомендациям по проектированию конструктора, которые не являются естественными.</span><span class="sxs-lookup"><span data-stu-id="75d48-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="75d48-115">✔️ использовать параметры конструктора в качестве сочетаний клавиш для задания основных свойств.</span><span class="sxs-lookup"><span data-stu-id="75d48-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="75d48-116">В семантике между использованием пустого конструктора, за которым следуют некоторые наборы свойств, и использование конструктора с несколькими аргументами не должно быть различий.</span><span class="sxs-lookup"><span data-stu-id="75d48-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="75d48-117">✔️ использовать одно и то же имя для параметров конструктора и свойство, если параметры конструктора используются для просто установки свойства.</span><span class="sxs-lookup"><span data-stu-id="75d48-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="75d48-118">Единственное различие между такими параметрами и свойствами должно быть в регистре.</span><span class="sxs-lookup"><span data-stu-id="75d48-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="75d48-119">✔️ ВЫПОЛНИТЬ минимальную работу в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="75d48-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="75d48-120">Конструкторы не должны выполнять много операций, кроме сбора параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="75d48-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="75d48-121">Стоимость любой другой обработки должна быть отложена до необходимости.</span><span class="sxs-lookup"><span data-stu-id="75d48-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="75d48-122">✔️ Вызывайте исключения из конструкторов экземпляров, если это уместно.</span><span class="sxs-lookup"><span data-stu-id="75d48-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="75d48-123">✔️ явно объявите открытый конструктор без параметров в классах, если такой конструктор является обязательным.</span><span class="sxs-lookup"><span data-stu-id="75d48-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="75d48-124">Если вы не объявили явно какие-либо конструкторы в типе, многие языки ( C#такие как) автоматически добавляют открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="75d48-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="75d48-125">(Абстрактные классы получают защищенный конструктор.)</span><span class="sxs-lookup"><span data-stu-id="75d48-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="75d48-126">Добавление параметризованного конструктора в класс не позволяет компилятору добавлять конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="75d48-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="75d48-127">Это часто приводит к случайным критическим изменениям.</span><span class="sxs-lookup"><span data-stu-id="75d48-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="75d48-128">❌ избежать явного определения конструкторов без параметров для структур.</span><span class="sxs-lookup"><span data-stu-id="75d48-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="75d48-129">Это делает создание массива быстрее, так как если конструктор без параметров не определен, он не должен выполняться в каждом слоте массива.</span><span class="sxs-lookup"><span data-stu-id="75d48-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="75d48-130">Обратите внимание, что многие компиляторы, включая C#, не разрешают структурам использовать конструкторы без параметров по этой причине.</span><span class="sxs-lookup"><span data-stu-id="75d48-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="75d48-131">❌ избежать вызова виртуальных членов для объекта внутри его конструктора.</span><span class="sxs-lookup"><span data-stu-id="75d48-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="75d48-132">Вызов виртуального члена приведет к вызову наиболее производного переопределения, даже если конструктор самого производного типа еще не был полностью запущен.</span><span class="sxs-lookup"><span data-stu-id="75d48-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="75d48-133">Рекомендации по конструктору типов</span><span class="sxs-lookup"><span data-stu-id="75d48-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="75d48-134">✔️ сделать статические конструкторы частными.</span><span class="sxs-lookup"><span data-stu-id="75d48-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="75d48-135">Статический конструктор, также называемый конструктором класса, используется для инициализации типа.</span><span class="sxs-lookup"><span data-stu-id="75d48-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="75d48-136">Среда CLR вызывает статический конструктор перед созданием первого экземпляра типа или вызовом любых статических членов этого типа.</span><span class="sxs-lookup"><span data-stu-id="75d48-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="75d48-137">Пользователь не может управлять при вызове статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="75d48-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="75d48-138">Если статический конструктор не является закрытым, он может быть вызван кодом, отличным от CLR.</span><span class="sxs-lookup"><span data-stu-id="75d48-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="75d48-139">В зависимости от операций, выполняемых в конструкторе, это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="75d48-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="75d48-140">C# Компилятор принудительно применяет к закрытию статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="75d48-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="75d48-141">❌ не вызывайте исключения из статических конструкторов.</span><span class="sxs-lookup"><span data-stu-id="75d48-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="75d48-142">Если исключение создается из конструктора типов, этот тип не может использоваться в текущем домене приложения.</span><span class="sxs-lookup"><span data-stu-id="75d48-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="75d48-143">✔️ Рассмотрите возможность инициализации статических полей встроенным способом, а не явно используя статические конструкторы, так как среда выполнения может оптимизировать производительность типов, у которых нет явно определенного статического конструктора.</span><span class="sxs-lookup"><span data-stu-id="75d48-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="75d48-144">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="75d48-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="75d48-145">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="75d48-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="75d48-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75d48-146">See also</span></span>

- [<span data-ttu-id="75d48-147">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="75d48-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="75d48-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="75d48-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
