---
title: Критические изменения и библиотеки .NET
description: Практические рекомендации по работе с критическими изменениями при создании библиотек .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 8536662ae1cd9733efbcc0c6526bd69d34a13177
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740986"
---
# <a name="breaking-changes"></a><span data-ttu-id="121a1-103">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="121a1-103">Breaking changes</span></span>

<span data-ttu-id="121a1-104">При разработке библиотеки .NET очень важно сохранять правильный баланс между стабильностью для существующих пользователей и возможностью реализации новых функций.</span><span class="sxs-lookup"><span data-stu-id="121a1-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="121a1-105">Авторы библиотек, как правило, стремятся довести код до совершенства, однако влияние на работу существующих пользователей имеет негативные последствия, особенно для библиотек низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="121a1-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="121a1-106">Типы проектов и критические изменения</span><span class="sxs-lookup"><span data-stu-id="121a1-106">Project types and breaking changes</span></span>

<span data-ttu-id="121a1-107">Способ использования библиотеки сообществом .NET определяет степень влияния критических изменений на работу конечных пользователей-разработчиков.</span><span class="sxs-lookup"><span data-stu-id="121a1-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

- <span data-ttu-id="121a1-108">**Библиотеки низкого и среднего уровня**, например сериализатор, средство синтаксического анализа HTML, объектно-реляционный модуль сопоставления баз данных или веб-платформа, чаще всего затрагиваются критическими изменениями.</span><span class="sxs-lookup"><span data-stu-id="121a1-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="121a1-109">Пакеты стандартных блоков используются конечными пользователями-разработчиками для создания приложений и другими библиотеками как зависимости NuGet.</span><span class="sxs-lookup"><span data-stu-id="121a1-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="121a1-110">Например, вы создаете приложение и используете клиент с открытым кодом для вызова веб-службы.</span><span class="sxs-lookup"><span data-stu-id="121a1-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="121a1-111">При этом вы не можете исправить критическое изменение для зависимости, используемой клиентом.</span><span class="sxs-lookup"><span data-stu-id="121a1-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="121a1-112">Это клиент с открытым кодом, который необходимо изменить, и вы не можете это контролировать.</span><span class="sxs-lookup"><span data-stu-id="121a1-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="121a1-113">Вам придется найти совместимые версии библиотек или отправить исправление в клиентскую библиотеку и дожидаться новой версии.</span><span class="sxs-lookup"><span data-stu-id="121a1-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="121a1-114">В худшем случае вам требуется использовать две библиотеки, которые зависят от взаимно несовместимых версий третьей библиотеки.</span><span class="sxs-lookup"><span data-stu-id="121a1-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

- <span data-ttu-id="121a1-115">**Высокоуровневые библиотеки**, такие как набор элементов управления пользовательского интерфейса, менее чувствительны к критическим изменениям.</span><span class="sxs-lookup"><span data-stu-id="121a1-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="121a1-116">Ссылка на высокоуровневые библиотеки включается непосредственно в приложение конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="121a1-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="121a1-117">При возникновении критических изменений разработчик может обновить приложение до последней версии или изменить его для работы с критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="121a1-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="121a1-118">**✔ ПОДУМАЙТЕ️** о вариантах использования вашей библиотеки.</span><span class="sxs-lookup"><span data-stu-id="121a1-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="121a1-119">Какой эффект критические изменения окажут на приложения и библиотеки, которые его используют?</span><span class="sxs-lookup"><span data-stu-id="121a1-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="121a1-120">**✔️ СВЕДИТЕ** критические изменения к минимуму при разработке низкоуровневой библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="121a1-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="121a1-121">**✔ РАССМОТРИТЕ️** возможность публикации библиотеки как нового пакета NuGet вместо внесения большого числа изменений.</span><span class="sxs-lookup"><span data-stu-id="121a1-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="121a1-122">Типы критических изменений</span><span class="sxs-lookup"><span data-stu-id="121a1-122">Types of breaking changes</span></span>

<span data-ttu-id="121a1-123">Критические изменения делятся на разные категории, и их влияние неодинаково.</span><span class="sxs-lookup"><span data-stu-id="121a1-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="121a1-124">Критическое изменение исходного кода</span><span class="sxs-lookup"><span data-stu-id="121a1-124">Source breaking change</span></span>

<span data-ttu-id="121a1-125">Критическое изменение исходного кода не влияет на выполнение программы, но приводит к ошибкам компиляции при следующей повторной компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="121a1-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="121a1-126">Например, новая перегрузка может создавать неоднозначность при вызове методов, которые ранее были однозначными, или переименование параметра приведет к нарушению работы вызывающих объектов, использующих именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="121a1-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="121a1-127">Так как критическое изменение исходного кода опасно только при перекомпиляции приложений, оно считается наименее разрушительным критическим изменением.</span><span class="sxs-lookup"><span data-stu-id="121a1-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="121a1-128">Разработчики могут легко исправить собственный неработающий исходный код.</span><span class="sxs-lookup"><span data-stu-id="121a1-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="121a1-129">Критическое изменение поведения</span><span class="sxs-lookup"><span data-stu-id="121a1-129">Behavior breaking change</span></span>

<span data-ttu-id="121a1-130">Изменения в поведении являются наиболее распространенным типом критического изменения: почти любое изменение в поведении может нарушить работу тех или иных пользователей.</span><span class="sxs-lookup"><span data-stu-id="121a1-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="121a1-131">Изменения в библиотеке, например изменение сигнатур методов, создаваемые исключения или форматы входных или выходных данных, будут отрицательно воздействовать на потребителей библиотеки.</span><span class="sxs-lookup"><span data-stu-id="121a1-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="121a1-132">Даже исправление ошибки можно определить как критическое изменение, если работа пользователей зависела от прежнего некорректного поведения.</span><span class="sxs-lookup"><span data-stu-id="121a1-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="121a1-133">Добавление функций и улучшение некорректного поведения — это хорошо и правильно, однако если вы не примете должные меры, обновление может оказаться сложной задачей для существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="121a1-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="121a1-134">Одним из подходов, помогающих разработчикам в случае критических изменений поведения, является их скрытие за параметрами.</span><span class="sxs-lookup"><span data-stu-id="121a1-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="121a1-135">Параметры позволяют разработчикам обновить библиотеку до последней версии и в то же время согласиться или отказаться от критических изменений.</span><span class="sxs-lookup"><span data-stu-id="121a1-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="121a1-136">Эта стратегия позволяет разработчикам поддерживать актуальное состояние среды, при этом код, обращающийся к библиотеке, может адаптироваться со временем.</span><span class="sxs-lookup"><span data-stu-id="121a1-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="121a1-137">Например, MVC в ASP.NET Core использует концепцию [версии совместимости](/aspnet/core/mvc/compatibility-version), изменяющей включенные и отключенные функции в `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="121a1-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="121a1-138">**✔ РЕКОМЕНДУЕТСЯ** оставить новые функции отключенными по умолчанию, если они влияют на существующих пользователей, и дать разработчикам возможность соглашаться на включение функции с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="121a1-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="121a1-139">Критическое изменение двоичного кода</span><span class="sxs-lookup"><span data-stu-id="121a1-139">Binary breaking change</span></span>

<span data-ttu-id="121a1-140">Критическое изменение двоичного кода происходит при изменении открытого API-интерфейса библиотек так, что сборки, скомпилированные для более старых версий библиотеки, больше не могут вызывать API.</span><span class="sxs-lookup"><span data-stu-id="121a1-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="121a1-141">Например, изменение сигнатуры метода путем добавления нового параметра приведет к тому, что сборки, скомпилированные для более старой версии библиотеки, будут создавать исключение <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="121a1-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="121a1-142">Критическое изменение двоичного кода также может нарушить работу **всей сборки**.</span><span class="sxs-lookup"><span data-stu-id="121a1-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="121a1-143">Переименование сборки с помощью `AssemblyName` изменит удостоверение сборки, так же как и добавление, удаление или изменение ключа строгого именования сборки.</span><span class="sxs-lookup"><span data-stu-id="121a1-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="121a1-144">Изменение удостоверения сборки нарушит работу всего скомпилированного кода, который ее использует.</span><span class="sxs-lookup"><span data-stu-id="121a1-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="121a1-145">**❌ НЕЛЬЗЯ** изменять имя сборки.</span><span class="sxs-lookup"><span data-stu-id="121a1-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="121a1-146">**❌ НЕЛЬЗЯ.** Не добавляйте, не удаляйте и не изменяйте ключ строгого именования.</span><span class="sxs-lookup"><span data-stu-id="121a1-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="121a1-147">**✔️ РЕКОМЕНДУЕТСЯ** использовать абстрактные базовые классы вместо интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="121a1-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="121a1-148">Добавление каких-либо объектов в интерфейс вызовет сбой существующих типов, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="121a1-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="121a1-149">Абстрактный базовый класс позволяет добавлять виртуальную реализацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="121a1-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="121a1-150">**✔️ РЕКОМЕНДУЕТСЯ** использовать <xref:System.ObsoleteAttribute> для типов и членов, которые планируется удалить.</span><span class="sxs-lookup"><span data-stu-id="121a1-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="121a1-151">Этот атрибут должен иметь инструкции по обновлению кода, запрещающие использовать устаревший API.</span><span class="sxs-lookup"><span data-stu-id="121a1-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="121a1-152">Код, который вызывает типы и методы с атрибутом <xref:System.ObsoleteAttribute>, выдаст предупреждение сборки с сообщением, переданным в атрибут.</span><span class="sxs-lookup"><span data-stu-id="121a1-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="121a1-153">Предупреждения дают пользователям, использующим устаревший API, время для миграции. Таким образом, к моменту удаления устаревшего API большинство разработчиков не будет его использовать.</span><span class="sxs-lookup"><span data-stu-id="121a1-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

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

<span data-ttu-id="121a1-154">**✔️ РЕКОМЕНДУЕТСЯ** хранить типы и методы с атрибутом <xref:System.ObsoleteAttribute> в библиотеках низкого и среднего уровня бессрочно.</span><span class="sxs-lookup"><span data-stu-id="121a1-154">**✔️ CONSIDER** keeping types and methods with the <xref:System.ObsoleteAttribute> indefinitely in low and middle-level libraries.</span></span>

> <span data-ttu-id="121a1-155">Удаление API — это критическое изменение двоичного кода.</span><span class="sxs-lookup"><span data-stu-id="121a1-155">Removing APIs is a binary breaking change.</span></span> <span data-ttu-id="121a1-156">Рассмотрите возможность сохранения устаревших типов и методов, если оно не влечет за собой больших затрат и рост технического долга.</span><span class="sxs-lookup"><span data-stu-id="121a1-156">Considering keeping obsolete types and methods if maintaining them is low cost and doesn't add lot of technical debt to your library.</span></span> <span data-ttu-id="121a1-157">Отказ от удаления типов и методов может помочь избежать неблагоприятных ситуаций, упомянутых выше.</span><span class="sxs-lookup"><span data-stu-id="121a1-157">Not removing types and methods can help avoid the worst-case scenarios mentioned above.</span></span>

## <a name="see-also"></a><span data-ttu-id="121a1-158">См. также</span><span class="sxs-lookup"><span data-stu-id="121a1-158">See also</span></span>

- [<span data-ttu-id="121a1-159">Соображения относительно версии и обновления для разработчиков на C#</span><span class="sxs-lookup"><span data-stu-id="121a1-159">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
- [<span data-ttu-id="121a1-160">Полное руководство по критическим изменениям API в .NET</span><span class="sxs-lookup"><span data-stu-id="121a1-160">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
- [<span data-ttu-id="121a1-161">Правила критических изменений .NET</span><span class="sxs-lookup"><span data-stu-id="121a1-161">.NET breaking change rules</span></span>](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="121a1-162">Назад</span><span class="sxs-lookup"><span data-stu-id="121a1-162">Previous</span></span>](versioning.md)
