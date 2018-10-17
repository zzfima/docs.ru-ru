---
title: Критические изменения и библиотеки .NET
description: Практические рекомендации для перемещения по критические изменения, при создании библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370341"
---
# <a name="breaking-changes"></a><span data-ttu-id="950d8-103">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="950d8-103">Breaking changes</span></span>

<span data-ttu-id="950d8-104">Очень важно для библиотеки .NET найти баланс между стабильности для существующих пользователей и инновации в будущем.</span><span class="sxs-lookup"><span data-stu-id="950d8-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="950d8-105">Авторы библиотеки бережливого рефакторинг и Переосмысление кода, пока она идеально подходит, но критические существующим пользователям оказывает негативное влияние, особенно для библиотек низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="950d8-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="950d8-106">Типы проектов и критические изменения</span><span class="sxs-lookup"><span data-stu-id="950d8-106">Project types and breaking changes</span></span>

<span data-ttu-id="950d8-107">Использование библиотеки в сообществе .NET изменяет эффект изменений, нарушающих работу разработчиков, конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="950d8-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

* <span data-ttu-id="950d8-108">**Низкого и среднего уровня библиотеки** например сериализатор, средство синтаксического анализа HTML, объектно реляционным модулем сопоставления базы данных или веб-платформа являются наиболее пострадавших, критические изменения.</span><span class="sxs-lookup"><span data-stu-id="950d8-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="950d8-109">Стандартный блок пакетов используются конечным пользователем разработчикам создавать приложения и другие библиотеки как зависимостей NuGet.</span><span class="sxs-lookup"><span data-stu-id="950d8-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="950d8-110">К примеру вы создаете приложение и используете клиент с открытым кодом для вызова веб-службы.</span><span class="sxs-lookup"><span data-stu-id="950d8-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="950d8-111">В обновлении критические зависимости, в которую клиент использует не то, что вы можете исправить.</span><span class="sxs-lookup"><span data-stu-id="950d8-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="950d8-112">Это клиент с открытым кодом, который необходимо изменить, и у вас нет контроль над компьютером.</span><span class="sxs-lookup"><span data-stu-id="950d8-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="950d8-113">Вам нужно найти совместимые версии библиотек или отправить команду, чтобы клиентская библиотека и ожидать от новой версии.</span><span class="sxs-lookup"><span data-stu-id="950d8-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="950d8-114">Худшего случая ситуация, если вы хотите использовать две библиотеки, которые зависят от взаимно несовместимые версии третий библиотеки.</span><span class="sxs-lookup"><span data-stu-id="950d8-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

* <span data-ttu-id="950d8-115">**Высокоуровневые библиотеки** как набор пользовательского интерфейса элементов управления менее чувствительны к критические изменения.</span><span class="sxs-lookup"><span data-stu-id="950d8-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="950d8-116">Высокоуровневые библиотеки указываются непосредственно в приложение конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="950d8-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="950d8-117">При возникновении критических изменений, разработчик можете обновить до последней версии, или можно изменить их приложения для работы с критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="950d8-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="950d8-118">**СДЕЛАТЬ ✔️** подумайте об использовании библиотеки.</span><span class="sxs-lookup"><span data-stu-id="950d8-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="950d8-119">Какой эффект окажет критические изменения в приложения и библиотеки, которые используют его?</span><span class="sxs-lookup"><span data-stu-id="950d8-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="950d8-120">**СДЕЛАТЬ ✔️** свести к минимуму критических изменений при разработке это низкоуровневая библиотека .NET.</span><span class="sxs-lookup"><span data-stu-id="950d8-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="950d8-121">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** публикации основной переписать библиотеки как новый пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="950d8-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="950d8-122">Типы критические изменения</span><span class="sxs-lookup"><span data-stu-id="950d8-122">Types of breaking changes</span></span>

<span data-ttu-id="950d8-123">Критические изменения делятся на разные категории и не столь же важные тенденции.</span><span class="sxs-lookup"><span data-stu-id="950d8-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="950d8-124">Критическое изменение источника</span><span class="sxs-lookup"><span data-stu-id="950d8-124">Source breaking change</span></span>

<span data-ttu-id="950d8-125">Источник, критическое изменение не влияет на выполнение программы, но приводит к ошибкам компиляции в следующий раз повторной компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="950d8-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="950d8-126">Например новая перегрузка может создавать неоднозначность при вызове методов, которые ранее были однозначными или переименованный параметр приведет к разрыву вызывающих объектов, использующих именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="950d8-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="950d8-127">Так как источник, критическое изменение только опасные при разработчикам перекомпиляции своих приложений, они не наименее травмирующие критическое изменение.</span><span class="sxs-lookup"><span data-stu-id="950d8-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="950d8-128">Разработчики могут легко исправить свои собственные неработающих исходный код.</span><span class="sxs-lookup"><span data-stu-id="950d8-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="950d8-129">Критические изменения в работе</span><span class="sxs-lookup"><span data-stu-id="950d8-129">Behavior breaking change</span></span>

<span data-ttu-id="950d8-130">Изменения в поведении являются наиболее распространенным типом критическое изменение: почти любое изменение в поведении может нарушить кто-то.</span><span class="sxs-lookup"><span data-stu-id="950d8-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="950d8-131">Изменения в библиотеку, в подписи метода, исключения, исключение или входных или выходных данных форматов данных, все будут отрицательно воздействовать на ваши пользователей библиотеки.</span><span class="sxs-lookup"><span data-stu-id="950d8-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="950d8-132">Даже исправления ошибки можно определять как критические изменения, если применяли ранее неработающих поведение.</span><span class="sxs-lookup"><span data-stu-id="950d8-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="950d8-133">Добавлением функций и улучшение плохие очень удобно, но без внимания он может сделать его очень сложной задачей для существующих пользователей для обновления.</span><span class="sxs-lookup"><span data-stu-id="950d8-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="950d8-134">Чтобы скрыть их за параметры является одним из подходов к помогает разработчикам справиться с поведением, критические изменения.</span><span class="sxs-lookup"><span data-stu-id="950d8-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="950d8-135">Параметры позволяют разработчикам обновить до последней версии библиотеки, в то же время, решили согласиться или отказаться от критических изменений.</span><span class="sxs-lookup"><span data-stu-id="950d8-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="950d8-136">Эта стратегия позволяет разработчикам Оставайтесь в курсе событий при этом разрешив много кода адаптировать со временем.</span><span class="sxs-lookup"><span data-stu-id="950d8-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="950d8-137">Например, ASP.NET Core MVC использует концепцию [совместимости версии](/aspnet/core/mvc/compatibility-version) , изменяющий возможности включать и отключать на `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="950d8-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="950d8-138">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** опустить новые функции по умолчанию, если они влияют на существующих пользователей и позволяют разработчикам согласиться на функции с параметром.</span><span class="sxs-lookup"><span data-stu-id="950d8-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="950d8-139">Двоичный критическое изменение</span><span class="sxs-lookup"><span data-stu-id="950d8-139">Binary breaking change</span></span>

<span data-ttu-id="950d8-140">Двоичный файл, критическое изменение происходит при изменении открытого API-интерфейса библиотеки, чтобы сборки, скомпилированные для более старых версий библиотеки больше не можете для вызова API.</span><span class="sxs-lookup"><span data-stu-id="950d8-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="950d8-141">Например, изменение сигнатуры метода путем добавления нового параметра приведет к сборки, скомпилированные для более старой версии библиотеки для создания <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="950d8-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="950d8-142">Критическое изменение двоичный файл можно также вставить разрыв **всю сборку**.</span><span class="sxs-lookup"><span data-stu-id="950d8-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="950d8-143">Переименование сборки `AssemblyName` изменится удостоверения сборки, как добавлять, удалять или изменять ключ строгого именования сборки.</span><span class="sxs-lookup"><span data-stu-id="950d8-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="950d8-144">Изменение удостоверения сборки нарушит работу всех скомпилированный код, который его использует.</span><span class="sxs-lookup"><span data-stu-id="950d8-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="950d8-145">**❌ НЕ** изменить имя сборки.</span><span class="sxs-lookup"><span data-stu-id="950d8-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="950d8-146">**❌ НЕ** добавления, удаления или изменения ключа строгого именования.</span><span class="sxs-lookup"><span data-stu-id="950d8-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="950d8-147">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** вместо абстрактных базовых классов и интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="950d8-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="950d8-148">Добавление ничего в интерфейс вызовет существующие типы, реализующие к сбою.</span><span class="sxs-lookup"><span data-stu-id="950d8-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="950d8-149">Абстрактный базовый класс позволяет добавлять виртуальные реализацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="950d8-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="950d8-150">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** размещение <xref:System.ObsoleteAttribute> для типов и членов, которые вы собираетесь удалить.</span><span class="sxs-lookup"><span data-stu-id="950d8-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="950d8-151">Атрибут должен иметь инструкции по обновлению кода больше не использовать устаревшие API.</span><span class="sxs-lookup"><span data-stu-id="950d8-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="950d8-152">Код, который вызывает типы и методы с <xref:System.ObsoleteAttribute> выдаст предупреждение сборки с сообщением, предоставленные для атрибута.</span><span class="sxs-lookup"><span data-stu-id="950d8-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="950d8-153">Предупреждения предоставляют пользователям время поверхности устаревший API миграции таким образом, когда удаляется устаревший API, большинство больше не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="950d8-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a><span data-ttu-id="950d8-154">См. также</span><span class="sxs-lookup"><span data-stu-id="950d8-154">See also</span></span>

* [<span data-ttu-id="950d8-155">Рекомендации по версии и обновления для разработчиков на C#</span><span class="sxs-lookup"><span data-stu-id="950d8-155">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
* [<span data-ttu-id="950d8-156">Полное руководство по API-критические изменения в .NET</span><span class="sxs-lookup"><span data-stu-id="950d8-156">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [<span data-ttu-id="950d8-157">CoreFX критическое изменение правила</span><span class="sxs-lookup"><span data-stu-id="950d8-157">CoreFX Breaking Change Rules</span></span>](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[<span data-ttu-id="950d8-158">Назад</span><span class="sxs-lookup"><span data-stu-id="950d8-158">Previous</span></span>](./versioning.md)
