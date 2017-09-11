---
title: "Управление версиями в C# | Руководство по C#"
description: "Сведения о принципах работы управления версиями в C# и .NET"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.date: 01/08/2017
ms.topic: article
ms.prod: visual-studio-dev-14
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0b671333019c00abafcfb72533e30936f8fc6ad7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="versioning-in-c"></a><span data-ttu-id="f8d08-104">Управление версиями в C#</span><span class="sxs-lookup"><span data-stu-id="f8d08-104">Versioning in C#</span></span> #

<span data-ttu-id="f8d08-105">В этом учебнике вы получите представление об управлении версиями в .NET.</span><span class="sxs-lookup"><span data-stu-id="f8d08-105">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="f8d08-106">Кроме того, вы узнаете, какие факторы следует учитывать при управлении версиями библиотеки и обновлении до ее новой версии.</span><span class="sxs-lookup"><span data-stu-id="f8d08-106">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of the a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="f8d08-107">Разработка библиотек</span><span class="sxs-lookup"><span data-stu-id="f8d08-107">Authoring Libraries</span></span>

<span data-ttu-id="f8d08-108">Если вы занимались разработкой библиотек .NET для открытого использования, то, скорее всего, вам приходилось развертывать обновления.</span><span class="sxs-lookup"><span data-stu-id="f8d08-108">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="f8d08-109">Способ выполнения этой процедуры важен, так как необходимо обеспечить плавный перевод существующего кода на новую версию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f8d08-109">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="f8d08-110">Ниже описывается ряд моментов, которые следует учитывать при создании выпуска.</span><span class="sxs-lookup"><span data-stu-id="f8d08-110">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="f8d08-111">Семантическое управление версиями</span><span class="sxs-lookup"><span data-stu-id="f8d08-111">Semantic Versioning</span></span>

<span data-ttu-id="f8d08-112">[Семантическое версионирование](http://semver.org/) (SemVer) — это соглашение об именовании, применяемое к версиям библиотеки для обозначения ключевых вех.</span><span class="sxs-lookup"><span data-stu-id="f8d08-112">[Semantic versioning](http://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="f8d08-113">В идеале сведения о версии, включаемые в библиотеку, должны помочь разработчикам определить совместимость с проектами, в которых используются предыдущие версии этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f8d08-113">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="f8d08-114">Базовым вариантом SemVer является трехкомпонентный формат `MAJOR.MINOR.PATCH`, где:</span><span class="sxs-lookup"><span data-stu-id="f8d08-114">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>
 
* <span data-ttu-id="f8d08-115">`MAJOR` увеличивается при внесении изменений, приводящих к несовместимости API;</span><span class="sxs-lookup"><span data-stu-id="f8d08-115">`MAJOR` is incremented when you make incompatible API changes</span></span>
* <span data-ttu-id="f8d08-116">`MINOR` увеличивается при добавлении функциональных возможностей с обеспечением обратной совместимости;</span><span class="sxs-lookup"><span data-stu-id="f8d08-116">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
* <span data-ttu-id="f8d08-117">`PATCH` увеличивается при исправлении ошибок с обеспечением обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="f8d08-117">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="f8d08-118">При применении сведений о версии к библиотеке .NET возможны также и особые случаи, например, можно указать, что версия является предварительной и т. д.</span><span class="sxs-lookup"><span data-stu-id="f8d08-118">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="f8d08-119">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="f8d08-119">Backwards Compatibility</span></span>

<span data-ttu-id="f8d08-120">При выпуске новых версий библиотеки обеспечение обратной совместимости с предыдущими версиями, скорее всего, будет одной из основных задач.</span><span class="sxs-lookup"><span data-stu-id="f8d08-120">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="f8d08-121">Новая версия библиотеки является совместимой с предыдущей на уровне исходного кода, если код, который зависит от предыдущей версии, после перекомпиляции может работать с новой версией.</span><span class="sxs-lookup"><span data-stu-id="f8d08-121">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="f8d08-122">Новая версия библиотеки является совместимой на уровне двоичного кода, если приложение, которое зависело от предыдущей версии, может работать с новой версией без перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="f8d08-122">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="f8d08-123">Ниже описывается ряд моментов, которые следует учитывать при обеспечении обратной совместимости с предыдущими версиями библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f8d08-123">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

* <span data-ttu-id="f8d08-124">Виртуальные методы: когда вы делаете виртуальный метод невиртуальным в новой версии, это означает, что проекты, в которых этот метод переопределяется, необходимо будет обновить.</span><span class="sxs-lookup"><span data-stu-id="f8d08-124">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="f8d08-125">Это очень существенное изменение, которое настоятельно не рекомендуется производить.</span><span class="sxs-lookup"><span data-stu-id="f8d08-125">This is a huge breaking change and is strongly discouraged.</span></span>
* <span data-ttu-id="f8d08-126">Сигнатуры методов: если при изменении поведения метода также необходимо изменить его сигнатуру, вместо этого следует создать перегрузку, чтобы код, вызывающий этот метод, по-прежнему работал.</span><span class="sxs-lookup"><span data-stu-id="f8d08-126">Method signatures: When updating a method behaviour requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="f8d08-127">Прежнюю сигнатуру метода всегда можно настроить так, чтобы она вызывала новую сигнатуру, обеспечив тем самым согласованность реализаций.</span><span class="sxs-lookup"><span data-stu-id="f8d08-127">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
* <span data-ttu-id="f8d08-128">[Атрибут obsolete](programming-guide/concepts/attributes/common-attributes.md#Obsolete): с помощью этого атрибута можно указывать в коде классы или члены классов, которые являются нерекомендуемыми и, вероятно, будут удалены в будущих версиях.</span><span class="sxs-lookup"><span data-stu-id="f8d08-128">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span>
<span data-ttu-id="f8d08-129">Благодаря этому разработчики, использующие вашу библиотеку, будут лучше подготовлены к существенным изменениям.</span><span class="sxs-lookup"><span data-stu-id="f8d08-129">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
* <span data-ttu-id="f8d08-130">Необязательные аргументы метода: если вы делаете необязательные аргументы метода обязательными или меняете их значения по умолчанию, то код, который не задает эти аргументы, потребуется обновить.</span><span class="sxs-lookup"><span data-stu-id="f8d08-130">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>
> [!NOTE]
> <span data-ttu-id="f8d08-131">Если обязательные аргументы становятся необязательными, то, как правило, это не должно иметь особых последствий, особенно если при этом поведение метода не меняется.</span><span class="sxs-lookup"><span data-stu-id="f8d08-131">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behaviour.</span></span>

<span data-ttu-id="f8d08-132">Чем проще пользователям будет произвести обновление до новой версии библиотеки, тем скорее они это сделают.</span><span class="sxs-lookup"><span data-stu-id="f8d08-132">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="f8d08-133">Файл конфигурации приложения</span><span class="sxs-lookup"><span data-stu-id="f8d08-133">Application Configuration File</span></span>

<span data-ttu-id="f8d08-134">Как разработчик .NET вы, весьма вероятно, встречали [файл `app.config`](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) в большинстве типов проектов.</span><span class="sxs-lookup"><span data-stu-id="f8d08-134">As a .NET developer there's a very high chance you've encountered [the `app.config` file](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) present in most project types.</span></span>
<span data-ttu-id="f8d08-135">Этот простой файл конфигурации может очень упростить развертывание обновлений.</span><span class="sxs-lookup"><span data-stu-id="f8d08-135">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="f8d08-136">В общем случае библиотеки следует проектировать так, чтобы сведения, которые, скорее всего, будут меняться регулярно, хранились в файле `app.config`. Благодаря этому при изменении таких сведений достаточно будет заменить файл конфигурации предыдущей версии на новый, не перекомпилируя библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f8d08-136">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="f8d08-137">Использование библиотек</span><span class="sxs-lookup"><span data-stu-id="f8d08-137">Consuming Libraries</span></span>

<span data-ttu-id="f8d08-138">Если при разработке вы используете библиотеки .NET, созданные другими разработчиками, то, скорее всего, знаете, что новая версия библиотеки может быть не полностью совместима с вашим проектом. В таком случае приходится обновлять код в соответствии с изменениями в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="f8d08-138">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="f8d08-139">К счастью, экосистема C# и .NET предоставляет возможности и методы, которые позволяют обновлять приложения для работы с новыми версиями библиотек, в которые были внесены существенные изменения.</span><span class="sxs-lookup"><span data-stu-id="f8d08-139">Lucky for you C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="f8d08-140">Перенаправление привязки сборок</span><span class="sxs-lookup"><span data-stu-id="f8d08-140">Assembly Binding Redirection</span></span>

<span data-ttu-id="f8d08-141">С помощью файла `app.config` можно изменить версию библиотеки, используемую приложением.</span><span class="sxs-lookup"><span data-stu-id="f8d08-141">You can use the `app.config` file to update the version of a library your app uses.</span></span> <span data-ttu-id="f8d08-142">Добавив так называемое [*перенаправление привязки*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx), вы можете использовать новую версию библиотеки, не перекомпилируя приложение.</span><span class="sxs-lookup"><span data-stu-id="f8d08-142">By adding what is called a [*binding redirect*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx) your can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="f8d08-143">В приведенном ниже примере показано, как можно изменить файл `app.config` приложения так, чтобы оно использовало версию исправления `1.0.1` библиотеки `ReferencedLibrary` вместо версии `1.0.0`, с которой оно изначально компилировалось.</span><span class="sxs-lookup"><span data-stu-id="f8d08-143">The following example shows how you would update your app's `app.config` file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="f8d08-144">Такой подход будет работать только в том случае, если новая версия библиотеки `ReferencedLibrary` совместима с приложением на уровне двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="f8d08-144">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="f8d08-145">Сведения об изменениях, на которые следует обращать внимание при определении совместимости, см. выше в подразделе [Обратная совместимость](#backwards-compatibility).</span><span class="sxs-lookup"><span data-stu-id="f8d08-145">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="f8d08-146">new</span><span class="sxs-lookup"><span data-stu-id="f8d08-146">new</span></span>

<span data-ttu-id="f8d08-147">Модификатор `new` служит для скрытия унаследованных членов базового класса.</span><span class="sxs-lookup"><span data-stu-id="f8d08-147">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="f8d08-148">Это один из способов, которым производные классы могут реагировать на изменения в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="f8d08-148">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="f8d08-149">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="f8d08-149">Take the following example:</span></span>

<span data-ttu-id="f8d08-150">[!code-csharp[Пример использования модификатора new](../../samples/csharp/versioning/new/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="f8d08-150">[!code-csharp[Sample usage of the 'new' modifier](../../samples/csharp/versioning/new/Program.cs#sample)]</span></span>

<span data-ttu-id="f8d08-151">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="f8d08-151">**Output**</span></span>

```
A base method
A derived method
```

<span data-ttu-id="f8d08-152">В приведенном выше примере можно видеть, как в классе `DerivedClass` скрывается метод `MyMethod`, имеющийся в классе `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="f8d08-152">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="f8d08-153">Таким образом, если в базовом классе в новой версии библиотеки появляется член, который уже имеется в вашем производном классе, можно просто использовать модификатор `new` для члена производного класса, чтобы скрыть соответствующий член базового класса.</span><span class="sxs-lookup"><span data-stu-id="f8d08-153">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="f8d08-154">Если модификатор `new` не указан, в производном классе будут по умолчанию скрываться конфликтующие члены базового класса. При этом будет выводиться предупреждение компилятора, однако код будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="f8d08-154">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="f8d08-155">Это означает, что добавление новых членов в существующий класс делает новую версию библиотеки совместимой с кодом, в котором она используется, на уровне как исходного, так и двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="f8d08-155">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="f8d08-156">override</span><span class="sxs-lookup"><span data-stu-id="f8d08-156">override</span></span>

<span data-ttu-id="f8d08-157">Модификатор `override` означает, что производная реализация расширяет реализацию члена базового класса, а не скрывает его.</span><span class="sxs-lookup"><span data-stu-id="f8d08-157">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="f8d08-158">К члену базового класса должен быть применен модификатор `virtual`.</span><span class="sxs-lookup"><span data-stu-id="f8d08-158">The base class member needs to have the `virtual` modifier applied to it.</span></span>

<span data-ttu-id="f8d08-159">[!code-csharp[Пример использования модификатора override](../../samples/csharp/versioning/override/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="f8d08-159">[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]</span></span>

<span data-ttu-id="f8d08-160">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="f8d08-160">**Output**</span></span>

```
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="f8d08-161">Модификатор `override` оценивается во время компиляции, и компилятор выдаст ошибку, если ему не удастся найти виртуальный член для переопределения.</span><span class="sxs-lookup"><span data-stu-id="f8d08-161">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="f8d08-162">Знание рассмотренных приемов и ситуаций, в которых их следует применять, поможет вам значительно упростить переход с одной версии библиотеки на другую.</span><span class="sxs-lookup"><span data-stu-id="f8d08-162">Your knowledge of the discussed techniques as well as your understanding of what situations to use them will go a long way to boost the ease of transition between versions of a library.</span></span>

