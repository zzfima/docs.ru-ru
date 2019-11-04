---
title: Оценка критических изменений (.NET Core)
description: Узнайте, какими методами в .NET Core обеспечивается совместимость между версиями .NET. для разработчиков.
ms.date: 06/10/2019
ms.openlocfilehash: a4a1b5c4e81cec783248c6110b0af9844eb3f4af
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73416682"
---
# <a name="evaluate-breaking-changes-in-net-core"></a><span data-ttu-id="0d6b9-103">Оценка критических изменений в .NET Core</span><span class="sxs-lookup"><span data-stu-id="0d6b9-103">Evaluate breaking changes in .NET Core</span></span>

<span data-ttu-id="0d6b9-104">На протяжении всей истории своего развития в .NET по возможности поддерживался высокий уровень совместимости между версиями и вариантами этой платформы.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="0d6b9-105">Этот подход сохраняется и для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="0d6b9-106">Хотя .NET Core можно считать новой технологией, которая не зависит от .NET Framework, возможность независимого от .NET Framework развития .NET Core ограничивается следующими двумя факторами:</span><span class="sxs-lookup"><span data-stu-id="0d6b9-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="0d6b9-107">Большое количество разработчиков разрабатывали ранее и продолжают разрабатывать приложения для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="0d6b9-108">Все они рассчитывают на согласованное поведение разных реализаций .NET.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="0d6b9-109">Проекты библиотек .NET Standard позволяют разработчикам создавать библиотеки для распространенных API, которые совместно используются в .NET Core и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="0d6b9-110">Разработчики ожидают, что библиотеки из приложения .NET Core будут вести себя точно так же, как аналогичные библиотеки в приложении .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="0d6b9-111">Кроме совместимости разных реализаций .NET, разработчики также ожидают высокий уровень совместимости между версиями .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="0d6b9-112">В частности, код, написанный для более ранней версии .NET Core, должен без проблем работать в любой последующей версии .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="0d6b9-113">Более того, многие разработчики ожидают, что новые API в свежих версиях .NET Core будут также совместимы с предварительными версиями, в которых впервые появились эти API.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="0d6b9-114">В этой статье описаны категории изменений, влияющих на совместимость (критических изменений), и методы оценки, которые использует команда .NET для каждой из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="0d6b9-115">Понимать подход, который команда разработчиков .NET использует для оценки возможных критических изменений, особенно важно для тех специалистов, которые создают в репозитории GitHub [dotnet/corefx](https://github.com/dotnet/corefx) запросы на вытягивание с изменением поведения существующих API.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who are opening pull requests in the [dotnet/corefx](https://github.com/dotnet/corefx) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="0d6b9-116">См. [определения категорий совместимости, таких как совместимость на уровне двоичного кода и обратная совместимость](categories.md).</span><span class="sxs-lookup"><span data-stu-id="0d6b9-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="0d6b9-117">В следующих разделах описываются категории изменений, внесенных в API .NET Core, и их влияние на совместимость приложений.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="0d6b9-118">Значок ✔️ указывает, что изменение разрешено; значок ❌ означает, что изменение запрещено; а значок ❓ обозначает изменение, которое может быть разрешено или запрещено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="0d6b9-119">Для изменений в этой последней категории требуется оценочное суждение о предсказуемости и очевидности, а также согласованности таких изменений с прежним поведением.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-119">Changes in this last category require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="0d6b9-120">Эти критерии для разработчиков библиотек служат не только руководством по оценке изменений в библиотеках .NET Core, но и помогают оценить изменения в собственных библиотеках, которые предназначены для разных реализаций и версий .NET.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="0d6b9-121">Изменения в открытом контракте</span><span class="sxs-lookup"><span data-stu-id="0d6b9-121">Modifications to the public contract</span></span>

<span data-ttu-id="0d6b9-122">Изменения в этой категории *изменяют* общую контактную зону для типа.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-122">Changes in this category *modify* the public surface area of a type.</span></span> <span data-ttu-id="0d6b9-123">Большинство изменений в этой категории запрещены, так как они нарушают *обратную совместимость* (возможность выполнять приложения, разработанные для предыдущих версий API, без повторной компиляции для более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="0d6b9-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="0d6b9-124">Типы</span><span class="sxs-lookup"><span data-stu-id="0d6b9-124">Types</span></span>

- <span data-ttu-id="0d6b9-125">**✔️ Удаление реализации интерфейса из типа, если этот интерфейс уже реализован в базовом типе**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="0d6b9-126">**❓Добавление новой реализации интерфейса в тип**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="0d6b9-127">Это допустимое изменение, так как оно не сказывается отрицательно на существующих клиентах.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="0d6b9-128">Чтобы новая реализация оставалась допустимой, любые изменения типа должны выполняться в пределах допустимых изменений, которые определены здесь.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="0d6b9-129">Следует соблюдать предельную осторожность при добавлении интерфейсов, которые напрямую влияют на способность конструктора или сериализатора создавать код или данные, которые нельзя использовать на нижнем уровне.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="0d6b9-130">Пример — интерфейс <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="0d6b9-131">**❓ Добавление нового базового класса**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="0d6b9-132">Тип можно включать в иерархию между двумя существующими типами, если он не включает новые [абстрактные](../../csharp/language-reference/keywords/abstract.md) элементы и не изменяет семантику или поведение существующих типов.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="0d6b9-133">Например, в .NET Framework 2.0 класс <xref:System.Data.Common.DbConnection> стал новым базовым классом для <xref:System.Data.SqlClient.SqlConnection> с наследованием напрямую от <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="0d6b9-134">**✔️ Перемещение типа из одной сборки в другую**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="0d6b9-135">Обратите внимание, что *старой* сборке следует присвоить метку <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>, указывающую на новую сборку.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="0d6b9-136">**✔️ Изменение типа [struct](../../csharp/language-reference/keywords/struct.md) на тип `readonly struct`**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="0d6b9-137">Обратите внимание, что изменение типа `readonly struct` на тип `struct` запрещено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>
  
- <span data-ttu-id="0d6b9-138">**✔️ Добавление ключевых слов [sealed](../../csharp/language-reference/keywords/sealed.md) или [abstract](../../csharp/language-reference/keywords/abstract.md) к типу, в котором нет *доступных* конструкторов (открытых или защищенных)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="0d6b9-139">**✔️ Расширение видимости типа**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="0d6b9-140">**❌ Изменение пространства имен или имени типа**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="0d6b9-141">**❌ Переименование или удаление открытого типа**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="0d6b9-142">Это изменение нарушает весь код, в котором использовался переименованный или удаленный тип.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="0d6b9-143">**❌ Изменение базового типа для перечисления**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="0d6b9-144">Это критическое изменение нарушает процесс компиляции и поведение приложения, а также совместимость на двоичном уровне вплоть до невозможности анализировать аргументы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="0d6b9-145">**❌ Запечатывание типа, который ранее был незапечатанным**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="0d6b9-146">**❌ Добавление интерфейса в набор базовых типов интерфейса**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="0d6b9-147">Если интерфейс реализует другой интерфейс, который ранее не был в нем реализован, нарушаются все типы, которые реализовали исходную версию этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="0d6b9-148">**❓Удаление класса из набора базовых классов или интерфейса из набора реализованных интерфейсов**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="0d6b9-149">Есть одно исключение из правила удаления интерфейса: вы можете добавить реализацию интерфейса, наследуемую от удаленного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="0d6b9-150">Например, можно удалить <xref:System.IDisposable>, если тип или интерфейс теперь реализуют <xref:System.ComponentModel.IComponent> с реализацией <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="0d6b9-151">**❌ Изменение типа `readonly struct` на тип [struct](../../csharp/language-reference/keywords/struct.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="0d6b9-152">Обратите внимание, что изменение типа `struct` на тип `readonly struct` разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="0d6b9-153">**❌ Изменение типа [struct](../../csharp/language-reference/keywords/struct.md) на тип `ref struct` и наоборот**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="0d6b9-154">**❌ Снижение видимости типа**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="0d6b9-155">При этом увеличение видимости типа разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="0d6b9-156">Участники</span><span class="sxs-lookup"><span data-stu-id="0d6b9-156">Members</span></span>

- <span data-ttu-id="0d6b9-157">**✔️ Расширение видимости для элемента, который не является [виртуальным](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="0d6b9-158">**✔️ Добавление абстрактного элемента в открытый тип без *доступных* конструкторов (открытых или защищенных) или в [запечатанный тип](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="0d6b9-159">При этом добавление абстрактного элемента в тип с доступными конструкторами (открытыми или защищенными) и в незапечатанный тип (`sealed`) разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="0d6b9-160">**✔️ Ограничение видимости [защищенного](../../csharp/language-reference/keywords/protected.md) элемента, если у типа нет доступных (открытых или защищенных) конструкторов или этот тип [запечатан](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="0d6b9-161">**✔️ Перемещение элемента в класс, расположенный в иерархии выше тип, из которого он был удален**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="0d6b9-162">**✔️ Добавление или удаление переопределения**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="0d6b9-163">Обратите внимание, что добавление переопределения может привести к тому, что прежние пользователи не будут его использовать при вызове [базового](../../csharp/language-reference/keywords/base.md) типа.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="0d6b9-164">**✔️ Добавление в класс конструктора одновременно с конструктором по умолчанию (без параметров), если ранее у этого класса не было конструкторов**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-164">**✔️ Adding a constructor to a class, along with a default (parameterless) constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="0d6b9-165">При этом добавление конструктора в класс, ранее не имевший конструкторов, *без* добавления конструктора без параметров, не разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-165">However, adding a constructor to a class that previously had no constructors *without* adding the parameterless constructor is not allowed.</span></span>

- <span data-ttu-id="0d6b9-166">**✔️ Изменение [абстрактного](../../csharp/language-reference/keywords/abstract.md) элемента на [виртуальный](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="0d6b9-167">**✔️ Изменение возвращаемого значения с `ref readonly` на `ref` (за исключением виртуальных методов или интерфейсов)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="0d6b9-168">**✔️ Удаление из поля метки [readonly](../../csharp/language-reference/keywords/readonly.md), за исключением полей со статическим типом изменяемого значения**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="0d6b9-169">**✔️ Вызов нового события, которое не было определено ранее**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="0d6b9-170">**❓ Добавление нового поля экземпляра к типу**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="0d6b9-171">Это изменение влияет на сериализацию.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-171">This change impacts serialization.</span></span>

- <span data-ttu-id="0d6b9-172">**❌ Переименование или удаление открытого типа или параметра**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="0d6b9-173">Это изменение нарушает весь код, в котором использовался переименованный или удаленный элемент либо параметр.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="0d6b9-174">Обратите внимание, что сюда относятся удаление и переименование методов получения и определения свойств, а также элементов перечисления.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="0d6b9-175">**❌ Добавление элемента к интерфейсу**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="0d6b9-176">**❌ Изменение значения общедоступной константы или элемента перечисления**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="0d6b9-177">**❌ Изменение типа для свойства, поля, параметра или возвращаемого значения**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="0d6b9-178">**❌ Добавление, удаление параметров или изменение их порядка**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="0d6b9-179">**❌ Добавление или удаление ключевого слова [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) или [ref](../../csharp/language-reference/keywords/ref.md) для параметра**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="0d6b9-180">**❌ Переименование параметра (в том числе изменение регистра символов)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="0d6b9-181">Такое изменение считается критическим по двум причинам:</span><span class="sxs-lookup"><span data-stu-id="0d6b9-181">This is considered breaking for two reasons:</span></span>
  
  - <span data-ttu-id="0d6b9-182">Оно нарушает сценарии с поздним связыванием, например функцию поздней привязки в Visual Basic и функцию [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) в C#.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.</span></span>
  
  - <span data-ttu-id="0d6b9-183">Оно нарушает [совместимость на уровне кода](categories.md#source-compatibility), если разработчик использует [именованные аргументы](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span><span class="sxs-lookup"><span data-stu-id="0d6b9-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="0d6b9-184">**❌ Изменение возвращаемого значения с `ref` на `ref readonly`**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="0d6b9-185">**❌ Изменение возвращаемого значения с `ref readonly` на `ref` для виртуальных методов или интерфейсов**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="0d6b9-186">**❌ Добавление или удаление ключевого слова [abstract](../../csharp/language-reference/keywords/abstract.md) для элемента**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="0d6b9-187">**❌ Удаление ключевого слова [virtual](../../csharp/language-reference/keywords/virtual.md) для элемента**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="0d6b9-188">Такое изменение часто не является критическим, так как компилятор C# обычно выдает инструкции [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) на промежуточном языке (IL) для вызова невиртуальных методов (`callvirt`, в отличие об обычного кода, выполняет проверку значений null). При этом такое поведение не может считаться стабильным по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="0d6b9-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="0d6b9-189">.NET используется не только с C#, но и с другими языками.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-189">C# is not the only language that .NET targets.</span></span>
  
  - <span data-ttu-id="0d6b9-190">Компилятор C# продолжает попытки оптимизировать `callvirt` в обычный вызов, если целевой метод не является виртуальным и с высокой вероятностью не имеет значения null (например, метод с доступом с использованием [оператора распространения значений null ?.](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span><span class="sxs-lookup"><span data-stu-id="0d6b9-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>
  
  <span data-ttu-id="0d6b9-191">Преобразование метода в виртуальный означает, что код объекта-получателя будет часто вызывать его не виртуально.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="0d6b9-192">**❌ Добавление ключевого слова [virtual](../../csharp/language-reference/keywords/virtual.md) к элементу**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="0d6b9-193">**❌ Преобразование виртуального элемента в абстрактный**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="0d6b9-194">[Виртуальный элемент](../../csharp/language-reference/keywords/virtual.md) предоставляет реализацию метода, которую *можно* переопределить производным классом.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="0d6b9-195">[Абстрактный элемент](../../csharp/language-reference/keywords/abstract.md) не предоставляет реализацию и *должен быть* переопределен.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="0d6b9-196">**❌ Добавление абстрактного элемента в общедоступный тип с доступными конструкторами (открытыми или защищенными) и [незапечатанный тип](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="0d6b9-197">**❌ Добавление в элемент ключевого слова [static](../../csharp/language-reference/keywords/static.md) или его удаление**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="0d6b9-198">**❌ Добавление перегрузки, которая исключает существующую перегрузку и определяет другое поведение**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="0d6b9-199">Такое изменение нарушает логику существующих клиентов, которые зависели от предыдущей перегрузки.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="0d6b9-200">Например, если у класса есть одна версия метода, которая принимает <xref:System.UInt32>, существующий получатель будет успешно привязан к этой перегрузке при отправке значения <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="0d6b9-201">Но если вы добавите перегрузку, которая принимает <xref:System.Int32>, при повторной компиляции или при использовании позднего связывания компилятор будет выполнять привязку к новой перегрузке.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="0d6b9-202">Любые изменения, приводящие к разным реакциям на события, считаются критическими.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="0d6b9-203">**❌ Добавление конструктора в класс, ранее не имевший конструкторов, без добавления конструктора без параметров**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-203">**❌ Adding a constructor to a class that previously had no constructor without adding the parameterless constructor**</span></span>

- <span data-ttu-id="0d6b9-204">**❌ Добавление ключевого слова [readonly](../../csharp/language-reference/keywords/readonly.md) в поле**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="0d6b9-205">**❌ Снижение видимости элемента**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="0d6b9-206">Сюда входит ограничение видимости [защищенного](../../csharp/language-reference/keywords/protected.md) элемента, если у типа нет *доступных* (открытых или защищенных) конструкторов или этот тип *не является* [запечатанным](../../csharp/language-reference/keywords/sealed.md).</span><span class="sxs-lookup"><span data-stu-id="0d6b9-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="0d6b9-207">Если это не так, снижение видимости защищенного элемента разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="0d6b9-208">Обратите внимание, что увеличение видимости типа разрешено.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="0d6b9-209">**❌ Изменение типа элемента**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="0d6b9-210">Возвращаемое значение метода или типа свойства или поля изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="0d6b9-211">Например, сигнатуру метода, который возвращает <xref:System.Object>, нельзя изменить так, чтобы он возвращал <xref:System.String>, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="0d6b9-212">**❌ Добавление поля к структуре, у которой ранее не было состояний**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="0d6b9-213">Правила определенного назначения допускают использование неинициализированных переменных, если переменная имеет тип структуры без отслеживания состояния.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="0d6b9-214">Если этой структуре добавить отслеживание состояния, код может получить неинициализированные данные.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="0d6b9-215">Такое изменение может быть критическим на уровне источника и двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="0d6b9-216">**❌ Вызов существующего события, которое ранее никогда не срабатывало**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="0d6b9-217">Изменения в поведении</span><span class="sxs-lookup"><span data-stu-id="0d6b9-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="0d6b9-218">Сборки</span><span class="sxs-lookup"><span data-stu-id="0d6b9-218">Assemblies</span></span>

- <span data-ttu-id="0d6b9-219">**✔️ Преобразование сборки в переносимую при сохранении поддержки тех же платформ**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="0d6b9-220">**❌ Изменение имени сборки**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="0d6b9-221">**❌ Изменение открытого ключа сборки**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="0d6b9-222">Свойства, поля, параметры и возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="0d6b9-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="0d6b9-223">**✔️ Изменение значения для свойства, поля, возвращаемого значения или параметра [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) на более производный тип**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="0d6b9-224">Например, метод, возвращающий тип <xref:System.Object>, может возвращать экземпляр <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="0d6b9-225">(Но при этом сигнатура метода не должна изменяться.)</span><span class="sxs-lookup"><span data-stu-id="0d6b9-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="0d6b9-226">**✔️ Увеличение диапазона допустимых значений для свойства или параметра, если элемент не является [виртуальным](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="0d6b9-227">Обратите внимание, что можно расширять диапазон значений, которые передаются методу или возвращаются из него, но нельзя расширять тип параметра или элемента.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="0d6b9-228">Например, диапазон передаваемых методу значений можно расширить с 0–124 до 0–255, но нельзя изменить тип параметра с <xref:System.Byte> на <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="0d6b9-229">**❌ Увеличение диапазона допустимых значений для свойства или параметра, если элемент является [виртуальным](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="0d6b9-230">Такое изменение нарушает существующие переопределенные элементы, которые не будут правильно работать с расширенным диапазоном значений.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="0d6b9-231">**❌ Уменьшение диапазона допустимых значений для свойства или параметра**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="0d6b9-232">**❌ Увеличение диапазона допустимых значений для свойства, поля, возвращаемого значения или параметра [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="0d6b9-233">**❌ Изменение возвращаемых значений для свойства, поля, возвращаемого значения метода или параметра [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="0d6b9-234">**❌ Изменение значения по умолчанию для свойства, поля или параметра**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="0d6b9-235">**❌ Изменение точности числового возвращаемого значения**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="0d6b9-236">**❓ Изменение логики синтаксического анализ входных данных и создание новых исключений (даже если поведение синтаксического анализа не указано в документации**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="0d6b9-237">Исключения</span><span class="sxs-lookup"><span data-stu-id="0d6b9-237">Exceptions</span></span>

- <span data-ttu-id="0d6b9-238">**✔️ Вызов более производного исключения, чем существующие исключения**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="0d6b9-239">Так как новое исключение является подклассом существующего исключения, существующий код обработки исключений будет обрабатывать это исключение.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="0d6b9-240">Например, в .NET Framework 4 методы создания и получения языка и региональных параметров теперь вызывают исключение <xref:System.Globalization.CultureNotFoundException> вместо <xref:System.ArgumentException>, если не могут найти язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="0d6b9-241">Так как <xref:System.Globalization.CultureNotFoundException> является производным от <xref:System.ArgumentException>, это изменение считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="0d6b9-242">**✔️ Вызов конкретного исключения, чем <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="0d6b9-243">**✔️ Вызов исключения, которое считается неустранимым**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="0d6b9-244">Неустранимые исключения не нужно перехватывать, они попадают в обработчик catch-all на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="0d6b9-245">Это означает, что у пользователей нет кода, который перехватывает эти явные исключения.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="0d6b9-246">Неустранимыми считаются следующие исключения:</span><span class="sxs-lookup"><span data-stu-id="0d6b9-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="0d6b9-247">**✔️ Вызов нового исключения в новом пути кода**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="0d6b9-248">Исключения должны применяться только к новому пути кода, который выполняется с новыми значениями параметров или состоянием, и который невозможно выполнить в существующем коде, ориентированном на предыдущую версию.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="0d6b9-249">**✔️ Удаление исключения для более надежной работы или для нового сценария**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="0d6b9-250">Например, метод `Divide`, который ранее обрабатывал только положительные значения и вызвал исключение <xref:System.ArgumentOutOfRangeException>, можно изменить так, чтобы он поддерживал положительные и отрицательные значения без вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="0d6b9-251">**✔️ Изменение текста сообщения об ошибке**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="0d6b9-252">Разработчикам не следует полагаться на текст сообщения об ошибках, который изменяется еще и в зависимости от языка и региональных параметров пользователя.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="0d6b9-253">**❌ Вызов исключения в любом случае, кроме перечисленных выше**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="0d6b9-254">**❌ Удаление исключения в любом случае, кроме перечисленных выше**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="0d6b9-255">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d6b9-255">Attributes</span></span>

- <span data-ttu-id="0d6b9-256">**✔️ Изменение значения атрибута, который *не* является наблюдаемым**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="0d6b9-257">**❌ Изменение значения атрибута, который *является* наблюдаемым**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="0d6b9-258">**❓ Удаление атрибута**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="0d6b9-259">В большинстве случаев удаление атрибута (например, <xref:System.NonSerializedAttribute>) является критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="0d6b9-260">Поддержка платформ</span><span class="sxs-lookup"><span data-stu-id="0d6b9-260">Platform support</span></span>

- <span data-ttu-id="0d6b9-261">**✔️ Поддержка операции для платформы, которая ранее не поддерживалась**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="0d6b9-262">**❌ Прекращение поддержки или требование конкретного пакета обновления для операции, которая ранее поддерживалась для платформы**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="0d6b9-263">Изменения внутренней реализации</span><span class="sxs-lookup"><span data-stu-id="0d6b9-263">Internal implementation changes</span></span>

- <span data-ttu-id="0d6b9-264">**❓ Изменение контактной зоны внутреннего типа**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="0d6b9-265">Такие изменения обычно разрешены, хотя они изменяют закрытое отражение.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="0d6b9-266">Эти изменения могут быть не разрешены в некоторых случаях, если популярные сторонние библиотеки или большое количество разработчиков полагаются на внутренние API.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="0d6b9-267">**❓ Изменение внутренней реализации элемента**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="0d6b9-268">Такие изменения обычно разрешены, хотя они изменяют закрытое отражение.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="0d6b9-269">Эти изменения могут быть не разрешены в некоторых случаях, если код клиента часто зависит от закрытого отражения или если изменения связаны с нежелательными побочными эффектами.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="0d6b9-270">**✔️ Повышение производительности операции**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="0d6b9-271">Возможность изменять производительность операции очень важна, но такие изменения могут нарушить код, который зависит от текущей скорости операции.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="0d6b9-272">Это особенно важно для кода, который зависит от скорости выполнения асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="0d6b9-273">Обратите внимание, что изменение производительности не должно влиять на другие аспекты поведения API, в противном случае изменение будет считаться критическим.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="0d6b9-274">**✔️ Косвенное (и обычно отрицательное) изменение производительности операции**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="0d6b9-275">Если изменение не относится к категории критических по другим причинам, оно считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="0d6b9-276">Зачастую требуются дополнительные действия, включая дополнительные операции или операции, которые добавляют новые функции.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="0d6b9-277">Это почти всегда влияет на производительность, но может требоваться для правильной работы API.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="0d6b9-278">**❌ Преобразование синхронного API в асинхронный (и наоборот)**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="0d6b9-279">Изменения в коде</span><span class="sxs-lookup"><span data-stu-id="0d6b9-279">Code changes</span></span>

- <span data-ttu-id="0d6b9-280">**✔️ Добавление [params](../../csharp/language-reference/keywords/params.md) в параметр**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="0d6b9-281">**❌ Замена [структуры](../../csharp/language-reference/keywords/struct.md) на [класс](../../csharp/language-reference/keywords/class.md) и наоборот**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="0d6b9-282">**❌ Добавление ключевого слова [checked](../../csharp/language-reference/keywords/virtual.md) в блок кода**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="0d6b9-283">Такое изменение может привести к тому, что ранее правильно выполнявшийся код будет вызывать исключение <xref:System.OverflowException>, что является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="0d6b9-284">**❌ Удаление [params](../../csharp/language-reference/keywords/params.md) из параметра**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="0d6b9-285">**❌ Изменение порядка возникновения событий**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="0d6b9-286">Разработчики могут рассчитывать на то, что события будут срабатывать в определенном порядке, и создаваемый ими код часто зависит от этого порядка.</span><span class="sxs-lookup"><span data-stu-id="0d6b9-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="0d6b9-287">**❌ Удаление вызова события для конкретного действия**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="0d6b9-288">**❌ Изменение количества вызовов определенных событий**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="0d6b9-289">**❌ Добавление <xref:System.FlagsAttribute> к типу перечисления**</span><span class="sxs-lookup"><span data-stu-id="0d6b9-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
