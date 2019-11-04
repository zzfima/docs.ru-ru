---
title: Управление версиями в C# | Руководство по C#
description: Сведения о принципах работы управления версиями в C# и .NET
ms.date: 01/08/2017
ms.technology: csharp-advanced-concepts
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: 3fadbc1257ae758fc220685fa074a4fa68b20ba1
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039653"
---
# <a name="versioning-in-c"></a><span data-ttu-id="db9d1-103">Управление версиями в C\#</span><span class="sxs-lookup"><span data-stu-id="db9d1-103">Versioning in C\#</span></span>

<span data-ttu-id="db9d1-104">В этом учебнике вы получите представление об управлении версиями в .NET.</span><span class="sxs-lookup"><span data-stu-id="db9d1-104">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="db9d1-105">Кроме того, вы узнаете, какие факторы следует учитывать при управлении версиями библиотеки и обновлении до ее новой версии.</span><span class="sxs-lookup"><span data-stu-id="db9d1-105">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="db9d1-106">Разработка библиотек</span><span class="sxs-lookup"><span data-stu-id="db9d1-106">Authoring Libraries</span></span>

<span data-ttu-id="db9d1-107">Если вы занимались разработкой библиотек .NET для открытого использования, то, скорее всего, вам приходилось развертывать обновления.</span><span class="sxs-lookup"><span data-stu-id="db9d1-107">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="db9d1-108">Способ выполнения этой процедуры важен, так как необходимо обеспечить плавный перевод существующего кода на новую версию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="db9d1-108">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="db9d1-109">Ниже описывается ряд моментов, которые следует учитывать при создании выпуска.</span><span class="sxs-lookup"><span data-stu-id="db9d1-109">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="db9d1-110">Семантическое управление версиями</span><span class="sxs-lookup"><span data-stu-id="db9d1-110">Semantic Versioning</span></span>

<span data-ttu-id="db9d1-111">[Семантическое версионирование](https://semver.org/) (SemVer) — это соглашение об именовании, применяемое к версиям библиотеки для обозначения ключевых вех.</span><span class="sxs-lookup"><span data-stu-id="db9d1-111">[Semantic versioning](https://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="db9d1-112">В идеале сведения о версии, включаемые в библиотеку, должны помочь разработчикам определить совместимость с проектами, в которых используются предыдущие версии этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="db9d1-112">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="db9d1-113">Базовым вариантом SemVer является трехкомпонентный формат `MAJOR.MINOR.PATCH`, где:</span><span class="sxs-lookup"><span data-stu-id="db9d1-113">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>

- <span data-ttu-id="db9d1-114">`MAJOR` увеличивается при внесении изменений, приводящих к несовместимости API;</span><span class="sxs-lookup"><span data-stu-id="db9d1-114">`MAJOR` is incremented when you make incompatible API changes</span></span>
- <span data-ttu-id="db9d1-115">`MINOR` увеличивается при добавлении функциональных возможностей с обеспечением обратной совместимости;</span><span class="sxs-lookup"><span data-stu-id="db9d1-115">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
- <span data-ttu-id="db9d1-116">`PATCH` увеличивается при исправлении ошибок с обеспечением обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="db9d1-116">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="db9d1-117">При применении сведений о версии к библиотеке .NET возможны также и особые случаи, например, можно указать, что версия является предварительной и т. д.</span><span class="sxs-lookup"><span data-stu-id="db9d1-117">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="db9d1-118">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="db9d1-118">Backwards Compatibility</span></span>

<span data-ttu-id="db9d1-119">При выпуске новых версий библиотеки обеспечение обратной совместимости с предыдущими версиями, скорее всего, будет одной из основных задач.</span><span class="sxs-lookup"><span data-stu-id="db9d1-119">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="db9d1-120">Новая версия библиотеки является совместимой с предыдущей на уровне исходного кода, если код, который зависит от предыдущей версии, после перекомпиляции может работать с новой версией.</span><span class="sxs-lookup"><span data-stu-id="db9d1-120">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="db9d1-121">Новая версия библиотеки является совместимой на уровне двоичного кода, если приложение, которое зависело от предыдущей версии, может работать с новой версией без перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="db9d1-121">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="db9d1-122">Ниже описывается ряд моментов, которые следует учитывать при обеспечении обратной совместимости с предыдущими версиями библиотеки.</span><span class="sxs-lookup"><span data-stu-id="db9d1-122">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

- <span data-ttu-id="db9d1-123">Виртуальные методы. Когда вы делаете виртуальный метод невиртуальным в новой версии, это означает, что проекты, в которых этот метод переопределяется, необходимо будет обновить.</span><span class="sxs-lookup"><span data-stu-id="db9d1-123">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="db9d1-124">Это очень существенное изменение, которое настоятельно не рекомендуется производить.</span><span class="sxs-lookup"><span data-stu-id="db9d1-124">This is a huge breaking change and is strongly discouraged.</span></span>
- <span data-ttu-id="db9d1-125">Сигнатуры методов. Если при изменении поведения метода также необходимо изменить его сигнатуру, вместо этого следует создать перегрузку, чтобы код, вызывающий этот метод, по-прежнему работал.</span><span class="sxs-lookup"><span data-stu-id="db9d1-125">Method signatures: When updating a method behavior requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="db9d1-126">Прежнюю сигнатуру метода всегда можно настроить так, чтобы она вызывала новую сигнатуру, обеспечив тем самым согласованность реализаций.</span><span class="sxs-lookup"><span data-stu-id="db9d1-126">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
- <span data-ttu-id="db9d1-127">[Атрибут Obsolete.](programming-guide/concepts/attributes/common-attributes.md#Obsolete) С помощью этого атрибута можно указывать в коде классы или члены классов, которые являются нерекомендуемыми и, вероятно, будут удалены в будущих версиях.</span><span class="sxs-lookup"><span data-stu-id="db9d1-127">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span> <span data-ttu-id="db9d1-128">Благодаря этому разработчики, использующие вашу библиотеку, будут лучше подготовлены к существенным изменениям.</span><span class="sxs-lookup"><span data-stu-id="db9d1-128">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
- <span data-ttu-id="db9d1-129">Необязательные аргументы метода. Если вы делаете необязательные аргументы метода обязательными или меняете их значения по умолчанию, то код, который не задает эти аргументы, потребуется обновить.</span><span class="sxs-lookup"><span data-stu-id="db9d1-129">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>

> [!NOTE]
> <span data-ttu-id="db9d1-130">Если обязательные аргументы становятся необязательными, то, как правило, это не должно иметь особых последствий, особенно если при этом поведение метода не меняется.</span><span class="sxs-lookup"><span data-stu-id="db9d1-130">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behavior.</span></span>

<span data-ttu-id="db9d1-131">Чем проще пользователям будет произвести обновление до новой версии библиотеки, тем скорее они это сделают.</span><span class="sxs-lookup"><span data-stu-id="db9d1-131">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="db9d1-132">Файл конфигурации приложения</span><span class="sxs-lookup"><span data-stu-id="db9d1-132">Application Configuration File</span></span>

<span data-ttu-id="db9d1-133">Как разработчик .NET вы, весьма вероятно, встречали [файл `app.config`](../framework/configure-apps/file-schema/index.md) в большинстве типов проектов.</span><span class="sxs-lookup"><span data-stu-id="db9d1-133">As a .NET developer there's a very high chance you've encountered [the `app.config` file](../framework/configure-apps/file-schema/index.md) present in most project types.</span></span>
<span data-ttu-id="db9d1-134">Этот простой файл конфигурации может очень упростить развертывание обновлений.</span><span class="sxs-lookup"><span data-stu-id="db9d1-134">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="db9d1-135">В основном библиотеки следует проектировать так, чтобы сведения, которые, скорее всего, будут меняться регулярно, хранились в файле `app.config`. Благодаря этому при изменении таких сведений достаточно будет заменить файл конфигурации предыдущей версии на новый, не перекомпилируя библиотеку.</span><span class="sxs-lookup"><span data-stu-id="db9d1-135">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated, the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="db9d1-136">Использование библиотек</span><span class="sxs-lookup"><span data-stu-id="db9d1-136">Consuming Libraries</span></span>

<span data-ttu-id="db9d1-137">Если при разработке вы используете библиотеки .NET, созданные другими разработчиками, то, скорее всего, знаете, что новая версия библиотеки может быть не полностью совместима с вашим проектом. В таком случае приходится обновлять код в соответствии с изменениями в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="db9d1-137">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="db9d1-138">К счастью, экосистема C# и .NET предоставляет возможности и методы, которые позволяют обновлять приложения для работы с новыми версиями библиотек, в которые были внесены существенные изменения.</span><span class="sxs-lookup"><span data-stu-id="db9d1-138">Lucky for you, C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="db9d1-139">Перенаправление привязки сборок</span><span class="sxs-lookup"><span data-stu-id="db9d1-139">Assembly Binding Redirection</span></span>

<span data-ttu-id="db9d1-140">С помощью файла *app.config* можно изменить версию библиотеки, используемую приложением.</span><span class="sxs-lookup"><span data-stu-id="db9d1-140">You can use the *app.config* file to update the version of a library your app uses.</span></span> <span data-ttu-id="db9d1-141">Добавив так называемое [*перенаправление привязки*](../framework/configure-apps/redirect-assembly-versions.md), вы можете использовать новую версию библиотеки, не перекомпилируя приложение.</span><span class="sxs-lookup"><span data-stu-id="db9d1-141">By adding what is called a [*binding redirect*](../framework/configure-apps/redirect-assembly-versions.md), you can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="db9d1-142">В приведенном ниже примере показано, как можно изменить файл приложения *app.config* так, чтобы оно использовало версию исправления `1.0.1` библиотеки `ReferencedLibrary` вместо версии `1.0.0`, с которой оно изначально компилировалось.</span><span class="sxs-lookup"><span data-stu-id="db9d1-142">The following example shows how you would update your app's *app.config* file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="db9d1-143">Такой подход будет работать только в том случае, если новая версия библиотеки `ReferencedLibrary` совместима с приложением на уровне двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="db9d1-143">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="db9d1-144">Сведения об изменениях, на которые следует обращать внимание при определении совместимости, см. выше в подразделе [Обратная совместимость](#backwards-compatibility).</span><span class="sxs-lookup"><span data-stu-id="db9d1-144">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="db9d1-145">new</span><span class="sxs-lookup"><span data-stu-id="db9d1-145">new</span></span>

<span data-ttu-id="db9d1-146">Модификатор `new` служит для скрытия унаследованных членов базового класса.</span><span class="sxs-lookup"><span data-stu-id="db9d1-146">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="db9d1-147">Это один из способов, которым производные классы могут реагировать на изменения в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="db9d1-147">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="db9d1-148">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="db9d1-148">Take the following example:</span></span>

[!code-csharp[Sample usage of the 'new' modifier](~/samples/csharp/versioning/new/Program.cs#sample)]

<span data-ttu-id="db9d1-149">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="db9d1-149">**Output**</span></span>

```console
A base method
A derived method
```

<span data-ttu-id="db9d1-150">В приведенном выше примере можно видеть, как в классе `DerivedClass` скрывается метод `MyMethod`, имеющийся в классе `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="db9d1-150">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="db9d1-151">Таким образом, если в базовом классе в новой версии библиотеки появляется член, который уже имеется в вашем производном классе, можно просто использовать модификатор `new` для члена производного класса, чтобы скрыть соответствующий член базового класса.</span><span class="sxs-lookup"><span data-stu-id="db9d1-151">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="db9d1-152">Если модификатор `new` не указан, в производном классе будут по умолчанию скрываться конфликтующие члены базового класса. При этом будет выводиться предупреждение компилятора, однако код будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="db9d1-152">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="db9d1-153">Это означает, что добавление новых членов в существующий класс делает новую версию библиотеки совместимой с кодом, в котором она используется, на уровне как исходного, так и двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="db9d1-153">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="db9d1-154">override</span><span class="sxs-lookup"><span data-stu-id="db9d1-154">override</span></span>

<span data-ttu-id="db9d1-155">Модификатор `override` означает, что производная реализация расширяет реализацию члена базового класса, а не скрывает его.</span><span class="sxs-lookup"><span data-stu-id="db9d1-155">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="db9d1-156">К члену базового класса должен быть применен модификатор `virtual`.</span><span class="sxs-lookup"><span data-stu-id="db9d1-156">The base class member needs to have the `virtual` modifier applied to it.</span></span>

[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]

<span data-ttu-id="db9d1-157">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="db9d1-157">**Output**</span></span>

```console
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="db9d1-158">Модификатор `override` оценивается во время компиляции, и компилятор выдаст ошибку, если ему не удастся найти виртуальный член для переопределения.</span><span class="sxs-lookup"><span data-stu-id="db9d1-158">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="db9d1-159">Знание рассмотренных приемов и ситуаций, в которых их следует применять, поможет вам значительно упростить переход с одной версии библиотеки на другую.</span><span class="sxs-lookup"><span data-stu-id="db9d1-159">Your knowledge of the discussed techniques and your understanding of the situations in which to use them, will go a long way towards easing the transition between versions of a library.</span></span>
