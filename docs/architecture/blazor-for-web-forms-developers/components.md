---
title: Создание повторно используемых компонентов пользовательского интерфейса с помощью Блазор
description: Узнайте, как создавать повторно используемые компоненты пользовательского интерфейса с помощью Блазор и сравнить их с элементами управления веб-форм ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 79919b183a4eb759f0b27c97500ee71c9378770b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841963"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="55747-103">Создание повторно используемых компонентов пользовательского интерфейса с помощью Блазор</span><span class="sxs-lookup"><span data-stu-id="55747-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="55747-104">Одним из замечательных вещей ASP.NET Web Forms является то, как она позволяет инкапсулировать многократно используемые фрагменты кода пользовательского интерфейса в многократно используемые элементы управления ПОЛЬЗОВАТЕЛЬСКОГО интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55747-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="55747-105">Настраиваемые пользовательские элементы управления могут быть определены в разметке с помощью файлов *. ascx* .</span><span class="sxs-lookup"><span data-stu-id="55747-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="55747-106">Кроме того, можно создавать сложные серверные элементы управления в коде с полной поддержкой конструктора.</span><span class="sxs-lookup"><span data-stu-id="55747-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="55747-107">Блазор также поддерживает инкапсуляцию пользовательского интерфейса через *компоненты*.</span><span class="sxs-lookup"><span data-stu-id="55747-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="55747-108">Компонент:</span><span class="sxs-lookup"><span data-stu-id="55747-108">A component:</span></span>

- <span data-ttu-id="55747-109">— Это автономный фрагмент пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55747-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="55747-110">Поддерживает собственную логику состояния и отрисовки.</span><span class="sxs-lookup"><span data-stu-id="55747-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="55747-111">Может определять обработчики событий пользовательского интерфейса, выполнять привязку к входным данным и управлять собственным жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="55747-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="55747-112">Обычно определяется в файле с *расширением Razor* с помощью синтаксис Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="55747-113">Введение в Razor</span><span class="sxs-lookup"><span data-stu-id="55747-113">An introduction to Razor</span></span>

<span data-ttu-id="55747-114">Razor — это облегченный язык создания шаблонов разметки на основе HTML C#и.</span><span class="sxs-lookup"><span data-stu-id="55747-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="55747-115">С помощью Razor можно легко переходить между разметкой C# и кодом, чтобы определить логику отрисовки компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="55747-116">При компиляции файла *. Razor* логика отрисовки записывается структурированным образом в классе .NET.</span><span class="sxs-lookup"><span data-stu-id="55747-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="55747-117">Имя скомпилированного класса берется из имени файла *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="55747-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="55747-118">Пространство имен берется из пространства имен по умолчанию для проекта и пути к папке, либо можно явно указать пространство имен с помощью директивы `@namespace` (см. дополнительные директивы Razor ниже).</span><span class="sxs-lookup"><span data-stu-id="55747-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="55747-119">Логика отрисовки компонента создается с помощью обычной разметки HTML с динамической логикой, C#добавленной с помощью.</span><span class="sxs-lookup"><span data-stu-id="55747-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="55747-120">Символ `@` используется для перехода в C#.</span><span class="sxs-lookup"><span data-stu-id="55747-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="55747-121">Razor обычно является разумным, чтобы определить, когда вы переключились обратно на HTML.</span><span class="sxs-lookup"><span data-stu-id="55747-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="55747-122">Например, следующий компонент визуализирует `<p>` тег с текущим временем:</span><span class="sxs-lookup"><span data-stu-id="55747-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="55747-123">Чтобы явно указать начало и конец C# выражения, используйте круглые скобки:</span><span class="sxs-lookup"><span data-stu-id="55747-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="55747-124">Razor также упрощает использование C# потока управления в логике отрисовки.</span><span class="sxs-lookup"><span data-stu-id="55747-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="55747-125">Например, можно выполнить условное отображение HTML-кода следующим образом:</span><span class="sxs-lookup"><span data-stu-id="55747-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="55747-126">Вы также можете создать список элементов с помощью обычного C# цикла `foreach` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="55747-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>item.Text</li>
}
</ul>
```

<span data-ttu-id="55747-127">Директивы Razor, такие как директивы в ASP.NET Web Forms, управляют многими аспектами компиляции компонента Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="55747-128">Примеры включают в себя компонент:</span><span class="sxs-lookup"><span data-stu-id="55747-128">Examples include the component's:</span></span>

- <span data-ttu-id="55747-129">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="55747-129">Namespace</span></span>
- <span data-ttu-id="55747-130">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="55747-130">Base class</span></span>
- <span data-ttu-id="55747-131">Реализованные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="55747-131">Implemented interfaces</span></span>
- <span data-ttu-id="55747-132">Универсальные параметры</span><span class="sxs-lookup"><span data-stu-id="55747-132">Generic parameters</span></span>
- <span data-ttu-id="55747-133">Импортированные пространства имен</span><span class="sxs-lookup"><span data-stu-id="55747-133">Imported namespaces</span></span>
- <span data-ttu-id="55747-134">Маршруты</span><span class="sxs-lookup"><span data-stu-id="55747-134">Routes</span></span>

<span data-ttu-id="55747-135">Директивы Razor начинаются с `@` символа и обычно используются в начале новой строки в начале файла.</span><span class="sxs-lookup"><span data-stu-id="55747-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="55747-136">Например, директива `@namespace` определяет пространство имен компонента:</span><span class="sxs-lookup"><span data-stu-id="55747-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="55747-137">В следующей таблице перечислены различные директивы Razor, используемые в Блазор, и их эквиваленты ASP.NET веб-форм, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="55747-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="55747-138">Директива</span><span class="sxs-lookup"><span data-stu-id="55747-138">Directive</span></span>    |<span data-ttu-id="55747-139">Описание</span><span class="sxs-lookup"><span data-stu-id="55747-139">Description</span></span>|<span data-ttu-id="55747-140">Пример</span><span class="sxs-lookup"><span data-stu-id="55747-140">Example</span></span>|<span data-ttu-id="55747-141">Эквивалент веб-форм</span><span class="sxs-lookup"><span data-stu-id="55747-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="55747-142">Добавляет атрибут уровня класса в компонент</span><span class="sxs-lookup"><span data-stu-id="55747-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="55747-143">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="55747-143">None</span></span>|
|`@code`      |<span data-ttu-id="55747-144">Добавляет члены класса в компонент</span><span class="sxs-lookup"><span data-stu-id="55747-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="55747-145">Реализует указанный интерфейс</span><span class="sxs-lookup"><span data-stu-id="55747-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="55747-146">Использовать код программной части</span><span class="sxs-lookup"><span data-stu-id="55747-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="55747-147">Наследует от указанного базового класса</span><span class="sxs-lookup"><span data-stu-id="55747-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="55747-148">Внедряет службу в компонент.</span><span class="sxs-lookup"><span data-stu-id="55747-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="55747-149">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="55747-149">None</span></span>|
|`@layout`    |<span data-ttu-id="55747-150">Задает компонент макета для компонента</span><span class="sxs-lookup"><span data-stu-id="55747-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="55747-151">Задает пространство имен для компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="55747-152">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="55747-152">None</span></span>|
|`@page`      |<span data-ttu-id="55747-153">Указывает маршрут для компонента</span><span class="sxs-lookup"><span data-stu-id="55747-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="55747-154">Задает параметр универсального типа для компонента</span><span class="sxs-lookup"><span data-stu-id="55747-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="55747-155">Использовать код программной части</span><span class="sxs-lookup"><span data-stu-id="55747-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="55747-156">Указывает пространство имен для переноса в область</span><span class="sxs-lookup"><span data-stu-id="55747-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="55747-157">Добавление пространства имен в *файл Web. config*</span><span class="sxs-lookup"><span data-stu-id="55747-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="55747-158">Компоненты Razor также активно используют *атрибуты директивы* в элементах для управления различными аспектами компиляции компонентов (обработки событий, привязки данных, компонентов & ссылок на элементы и т. д.).</span><span class="sxs-lookup"><span data-stu-id="55747-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="55747-159">Все атрибуты директивы следуют общему универсальному синтаксису, в котором значения в круглых скобках являются необязательными:</span><span class="sxs-lookup"><span data-stu-id="55747-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="55747-160">В следующей таблице приведены различные атрибуты директив Razor, используемые в Блазор.</span><span class="sxs-lookup"><span data-stu-id="55747-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="55747-161">Атрибут</span><span class="sxs-lookup"><span data-stu-id="55747-161">Attribute</span></span>    |<span data-ttu-id="55747-162">Описание</span><span class="sxs-lookup"><span data-stu-id="55747-162">Description</span></span>|<span data-ttu-id="55747-163">Пример</span><span class="sxs-lookup"><span data-stu-id="55747-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="55747-164">Подготавливает к просмотру словарь атрибутов</span><span class="sxs-lookup"><span data-stu-id="55747-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="55747-165">Создает двустороннюю привязку данных</span><span class="sxs-lookup"><span data-stu-id="55747-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="55747-166">Добавляет обработчик событий для указанного события</span><span class="sxs-lookup"><span data-stu-id="55747-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="55747-167">Задает ключ, используемый алгоритмом сравнения для сохранения элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="55747-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="55747-168">Захватывает ссылку на компонент или HTML-элемент</span><span class="sxs-lookup"><span data-stu-id="55747-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="55747-169">Различные атрибуты директивы, используемые Блазор (`@onclick`, `@bind`, `@ref`и т. д.), описаны в разделах ниже и последующих главах.</span><span class="sxs-lookup"><span data-stu-id="55747-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="55747-170">Многие из синтаксисов, используемых в файлах *. aspx* и *. ascx* , имеют параллельные синтаксисы в Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="55747-171">Ниже приведено простое сравнение синтаксиса для веб-форм ASP.NET и Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="55747-172">Возможность</span><span class="sxs-lookup"><span data-stu-id="55747-172">Feature</span></span>                      |<span data-ttu-id="55747-173">веб-формы</span><span class="sxs-lookup"><span data-stu-id="55747-173">Web Forms</span></span>           |<span data-ttu-id="55747-174">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55747-174">Syntax</span></span>               |<span data-ttu-id="55747-175">Razor</span><span class="sxs-lookup"><span data-stu-id="55747-175">Razor</span></span>         |<span data-ttu-id="55747-176">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55747-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="55747-177">Директивы</span><span class="sxs-lookup"><span data-stu-id="55747-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="55747-178">Блоки кода</span><span class="sxs-lookup"><span data-stu-id="55747-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="55747-179">Выражения</span><span class="sxs-lookup"><span data-stu-id="55747-179">Expressions</span></span><br><span data-ttu-id="55747-180">(В кодировке HTML)</span><span class="sxs-lookup"><span data-stu-id="55747-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="55747-181">Неявные: `@`</span><span class="sxs-lookup"><span data-stu-id="55747-181">Implicit: `@`</span></span><br><span data-ttu-id="55747-182">Явное: `@()`</span><span class="sxs-lookup"><span data-stu-id="55747-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="55747-183">Комментарии</span><span class="sxs-lookup"><span data-stu-id="55747-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="55747-184">привязка данных,</span><span class="sxs-lookup"><span data-stu-id="55747-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="55747-185">Чтобы добавить члены в класс компонента Razor, используйте директиву `@code`.</span><span class="sxs-lookup"><span data-stu-id="55747-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="55747-186">Этот метод аналогичен использованию блока `<script runat="server">...</script>` в пользовательском элементе управления или странице веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="55747-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="55747-187">Поскольку Razor основан на C#, он должен быть скомпилирован из C# проекта (*CSPROJ*).</span><span class="sxs-lookup"><span data-stu-id="55747-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="55747-188">Файлы *. Razor* нельзя компилировать из проекта VB ( *. vbproj*).</span><span class="sxs-lookup"><span data-stu-id="55747-188">You can't compile *.razor* files from a VB project (*.vbproj*).</span></span> <span data-ttu-id="55747-189">Вы по-прежнему можете ссылаться на проекты VB из проекта Блазор.</span><span class="sxs-lookup"><span data-stu-id="55747-189">You can still reference VB projects from your Blazor project.</span></span> <span data-ttu-id="55747-190">Обратное тоже верно.</span><span class="sxs-lookup"><span data-stu-id="55747-190">The opposite is true too.</span></span>

<span data-ttu-id="55747-191">Полный справочник по синтаксис Razor см. в статье [синтаксис Razor Справочник по ASP.NET Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="55747-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="55747-192">Использование компонентов</span><span class="sxs-lookup"><span data-stu-id="55747-192">Use components</span></span>

<span data-ttu-id="55747-193">Помимо обычного HTML, компоненты также могут использовать другие компоненты как часть логики отрисовки.</span><span class="sxs-lookup"><span data-stu-id="55747-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="55747-194">Синтаксис использования компонента в Razor подобен использованию пользовательского элемента управления в приложении веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="55747-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="55747-195">Компоненты указываются с помощью тега элемента, соответствующего имени типа компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="55747-196">Например, можно добавить `Counter` компонент, например:</span><span class="sxs-lookup"><span data-stu-id="55747-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="55747-197">В отличие от веб-форм ASP.NET, компоненты в Блазор:</span><span class="sxs-lookup"><span data-stu-id="55747-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="55747-198">Не используйте префикс элемента (например, `asp:`).</span><span class="sxs-lookup"><span data-stu-id="55747-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="55747-199">Не требовать регистрации на странице или в *файле Web. config*.</span><span class="sxs-lookup"><span data-stu-id="55747-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="55747-200">Подумайте о таких компонентах Razor, как типы .NET, так как это именно то, что они представляют.</span><span class="sxs-lookup"><span data-stu-id="55747-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="55747-201">Если имеется ссылка на сборку, содержащую компонент, то компонент доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="55747-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="55747-202">Чтобы перенести пространство имен компонента в область, примените директиву `@using`:</span><span class="sxs-lookup"><span data-stu-id="55747-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="55747-203">Как видно в проектах Блазор по умолчанию, часто `@using` директивы помещаются в файл *_Imports. Razor* , чтобы они были импортированы во все файлы *Razor* в одном и том же каталоге и в дочерних каталогах.</span><span class="sxs-lookup"><span data-stu-id="55747-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="55747-204">Если пространство имен для компонента не находится в области, можно указать компонент, используя его полное имя типа, как в C#следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="55747-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="55747-205">Параметры компонентов</span><span class="sxs-lookup"><span data-stu-id="55747-205">Component parameters</span></span>

<span data-ttu-id="55747-206">В ASP.NET Web Forms можно передавать параметры и данные в элементы управления с помощью общедоступных свойств.</span><span class="sxs-lookup"><span data-stu-id="55747-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="55747-207">Эти свойства можно задать в разметке с помощью атрибутов или непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="55747-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="55747-208">Компоненты блазор работают аналогичным образом, хотя свойства компонентов также должны быть помечены атрибутом `[Parameter]`, чтобы считаться параметрами компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="55747-209">Следующий `Counter` компонент определяет параметр компонента с именем `IncrementAmount`, который можно использовать для указания величины приращения `Counter` при каждом нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="55747-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="55747-210">Чтобы указать параметр компонента в Блазор, используйте атрибут, как в ASP.NET Web Forms:</span><span class="sxs-lookup"><span data-stu-id="55747-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="55747-211">Обработчики событий</span><span class="sxs-lookup"><span data-stu-id="55747-211">Event handlers</span></span>

<span data-ttu-id="55747-212">Как веб-формы ASP.NET, так и Блазор предоставляют модель программирования на основе событий для обработки событий пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55747-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="55747-213">Примеры таких событий включают нажатия кнопок и ввод текста.</span><span class="sxs-lookup"><span data-stu-id="55747-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="55747-214">В ASP.NET Web Forms используются серверные элементы управления HTML для работы с событиями пользовательского интерфейса, предоставляемыми моделью DOM, или для выполнения событий, предоставляемых серверными веб-элементами управления.</span><span class="sxs-lookup"><span data-stu-id="55747-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="55747-215">События отображаются на сервере посредством запросов обратной передачи.</span><span class="sxs-lookup"><span data-stu-id="55747-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="55747-216">Рассмотрим следующие примеры кнопок веб-форм:</span><span class="sxs-lookup"><span data-stu-id="55747-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="55747-217">*Counter. ascx*</span><span class="sxs-lookup"><span data-stu-id="55747-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="55747-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="55747-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="55747-219">В Блазор можно зарегистрировать обработчики для событий пользовательского интерфейса DOM напрямую с помощью атрибутов директивы в форме `@on{event}`.</span><span class="sxs-lookup"><span data-stu-id="55747-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="55747-220">Заполнитель `{event}` представляет имя события.</span><span class="sxs-lookup"><span data-stu-id="55747-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="55747-221">Например, можно прослушивать нажатия кнопок следующим образом:</span><span class="sxs-lookup"><span data-stu-id="55747-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="55747-222">Обработчики событий могут принимать необязательный аргумент, относящийся к конкретному событию, для предоставления дополнительных сведений о событии.</span><span class="sxs-lookup"><span data-stu-id="55747-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="55747-223">Например, события мыши могут принимать `MouseEventArgs` аргумент, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="55747-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="55747-224">Вместо ссылки на группу методов для обработчика событий можно использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="55747-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="55747-225">Лямбда-выражение позволяет закрывать другие значения в области.</span><span class="sxs-lookup"><span data-stu-id="55747-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="55747-226">Обработчики событий могут выполняться синхронно или асинхронно.</span><span class="sxs-lookup"><span data-stu-id="55747-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="55747-227">Например, следующий обработчик событий `OnClick` выполняется асинхронно:</span><span class="sxs-lookup"><span data-stu-id="55747-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="55747-228">После обработки события компонент подготавливается к просмотру для учета изменений состояния компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="55747-229">При использовании асинхронных обработчиков событий компонент подготавливается к просмотру сразу после завершения выполнения обработчика.</span><span class="sxs-lookup"><span data-stu-id="55747-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="55747-230">После завершения асинхронного `Task` компонент *снова* готовится к просмотру.</span><span class="sxs-lookup"><span data-stu-id="55747-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="55747-231">Этот асинхронный режим выполнения позволяет визуализировать какой-либо соответствующий пользовательский интерфейс во время выполнения асинхронного `Task`.</span><span class="sxs-lookup"><span data-stu-id="55747-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="Get message">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="55747-232">Компоненты также могут определять собственные события, определяя параметр компонента типа `EventCallback<TValue>`.</span><span class="sxs-lookup"><span data-stu-id="55747-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="55747-233">Обратные вызовы событий поддерживают все разновидности обработчиков событий пользовательского интерфейса DOM: необязательные аргументы, синхронные или асинхронные, группы методов или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="55747-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="55747-234">привязка данных,</span><span class="sxs-lookup"><span data-stu-id="55747-234">Data binding</span></span>

<span data-ttu-id="55747-235">Блазор предоставляет простой механизм привязки данных из компонента пользовательского интерфейса к состоянию компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="55747-236">Этот подход отличается от функций в ASP.NET Web Forms для привязки данных из источников данных к элементам управления пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55747-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="55747-237">Мы обсудим обработку данных из различных источников данных в разделе " [Работа с данными](data.md) ".</span><span class="sxs-lookup"><span data-stu-id="55747-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="55747-238">Чтобы создать двустороннюю привязку данных от компонента пользовательского интерфейса к состоянию компонента, используйте атрибут директивы `@bind`.</span><span class="sxs-lookup"><span data-stu-id="55747-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="55747-239">В следующем примере значение флажка привязано к полю `isChecked`.</span><span class="sxs-lookup"><span data-stu-id="55747-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="55747-240">При подготовке компонента к просмотру значение флажка устанавливается равным значению поля `isChecked`.</span><span class="sxs-lookup"><span data-stu-id="55747-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="55747-241">Когда пользователь переключает флажок, срабатывает событие `onchange`, и в поле `isChecked` задается новое значение.</span><span class="sxs-lookup"><span data-stu-id="55747-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="55747-242">Синтаксис `@bind` в этом случае эквивалентен следующей разметке:</span><span class="sxs-lookup"><span data-stu-id="55747-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="55747-243">Чтобы изменить событие, используемое для привязки, используйте атрибут `@bind:event`.</span><span class="sxs-lookup"><span data-stu-id="55747-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="55747-244">Компоненты также могут поддерживать привязку данных к их параметрам.</span><span class="sxs-lookup"><span data-stu-id="55747-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="55747-245">Для привязки данных определите параметр обратного вызова события с тем же именем, что и у привязываемого параметра.</span><span class="sxs-lookup"><span data-stu-id="55747-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="55747-246">В имя добавляется суффикс "Changed".</span><span class="sxs-lookup"><span data-stu-id="55747-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="55747-247">*PasswordBox. Razor*</span><span class="sxs-lookup"><span data-stu-id="55747-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="55747-248">Чтобы связать привязку данных с базовым элементом пользовательского интерфейса, установите значение и обработайте событие непосредственно в элементе пользовательского интерфейса, а не с помощью атрибута `@bind`.</span><span class="sxs-lookup"><span data-stu-id="55747-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="55747-249">Чтобы выполнить привязку к параметру компонента, используйте атрибут `@bind-{Parameter}`, чтобы указать параметр, с которым необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="55747-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="55747-250">Изменения состояния</span><span class="sxs-lookup"><span data-stu-id="55747-250">State changes</span></span>

<span data-ttu-id="55747-251">Если состояние компонента изменилось за пределами обычного пользовательского интерфейса или обратного вызова события, компонент должен вручную сообщить, что он должен быть визуализирован повторно.</span><span class="sxs-lookup"><span data-stu-id="55747-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="55747-252">Чтобы сообщить о том, что состояние компонента изменилось, вызовите метод `StateHasChanged` для компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="55747-253">В приведенном ниже примере компонент отображает сообщение из службы `AppState`, которая может быть обновлена другими частями приложения.</span><span class="sxs-lookup"><span data-stu-id="55747-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="55747-254">Компонент регистрирует свой метод `StateHasChanged` с событием `AppState.OnChange`, чтобы компонент был подготовлен при каждом обновлении сообщения.</span><span class="sxs-lookup"><span data-stu-id="55747-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="55747-255">Жизненный цикл компонента</span><span class="sxs-lookup"><span data-stu-id="55747-255">Component lifecycle</span></span>

<span data-ttu-id="55747-256">Платформа веб-форм ASP.NET имеет четко определенные методы жизненного цикла для модулей, страниц и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="55747-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="55747-257">Например, следующий элемент управления реализует обработчики событий для событий жизненного цикла `Init`, `Load`и `UnLoad`:</span><span class="sxs-lookup"><span data-stu-id="55747-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="55747-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="55747-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="55747-259">Компоненты блазор также имеют четко определенный жизненный цикл.</span><span class="sxs-lookup"><span data-stu-id="55747-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="55747-260">Жизненный цикл компонента можно использовать для инициализации состояния компонента и реализации дополнительных поведений компонентов.</span><span class="sxs-lookup"><span data-stu-id="55747-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="55747-261">Все методы жизненного цикла компонента Блазор имеют как синхронные, так и асинхронные версии.</span><span class="sxs-lookup"><span data-stu-id="55747-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="55747-262">Визуализация компонента является синхронной.</span><span class="sxs-lookup"><span data-stu-id="55747-262">Component rendering is synchronous.</span></span> <span data-ttu-id="55747-263">Асинхронную логику нельзя выполнять в процессе подготовки компонента к просмотру.</span><span class="sxs-lookup"><span data-stu-id="55747-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="55747-264">Вся Асинхронная логика должна выполняться как часть метода жизненного цикла `async`.</span><span class="sxs-lookup"><span data-stu-id="55747-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="55747-265">Oninitiald</span><span class="sxs-lookup"><span data-stu-id="55747-265">OnInitialized</span></span>

<span data-ttu-id="55747-266">Методы `OnInitialized` и `OnInitializedAsync` используются для инициализации компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="55747-267">Обычно компонент инициализируется после его первого отображения.</span><span class="sxs-lookup"><span data-stu-id="55747-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="55747-268">После инициализации компонента он может быть визуализирован несколько раз, прежде чем он будет удален в конечном итоге.</span><span class="sxs-lookup"><span data-stu-id="55747-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="55747-269">Метод `OnInitialized` аналогичен событию `Page_Load` в ASP.NET страницах и элементах управления веб-форм.</span><span class="sxs-lookup"><span data-stu-id="55747-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="55747-270">Onparameters, параметр</span><span class="sxs-lookup"><span data-stu-id="55747-270">OnParametersSet</span></span>

<span data-ttu-id="55747-271">Методы `OnParametersSet` и `OnParametersSetAsync` вызываются, когда компонент получил параметры от родительского элемента, и значение присваиваются свойствам.</span><span class="sxs-lookup"><span data-stu-id="55747-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="55747-272">Эти методы выполняются после инициализации компонента и при *каждом отображении компонента*.</span><span class="sxs-lookup"><span data-stu-id="55747-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="55747-273">онафтеррендер</span><span class="sxs-lookup"><span data-stu-id="55747-273">OnAfterRender</span></span>

<span data-ttu-id="55747-274">Методы `OnAfterRender` и `OnAfterRenderAsync` вызываются после завершения подготовки компонента к просмотру.</span><span class="sxs-lookup"><span data-stu-id="55747-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="55747-275">Ссылки на элементы и компоненты заполняются в этот момент (Подробнее об этих концепциях см. ниже).</span><span class="sxs-lookup"><span data-stu-id="55747-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="55747-276">В данный момент интерактивное взаимодействие с браузером включено.</span><span class="sxs-lookup"><span data-stu-id="55747-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="55747-277">Взаимодействие с моделью DOM и выполнением JavaScript может безопасно выполняться.</span><span class="sxs-lookup"><span data-stu-id="55747-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="55747-278">`OnAfterRender` и `OnAfterRenderAsync` *не вызываются при предварительной отрисовке на сервере*.</span><span class="sxs-lookup"><span data-stu-id="55747-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="55747-279">Параметр `firstRender` `true` при первом отображении компонента; в противном случае его значение — `false`.</span><span class="sxs-lookup"><span data-stu-id="55747-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="55747-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="55747-280">IDisposable</span></span>

<span data-ttu-id="55747-281">Компоненты блазор могут реализовывать `IDisposable` для удаления ресурсов, когда компонент удаляется из пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55747-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="55747-282">Компонент Razor может реализовать `IDispose` с помощью директивы `@implements`:</span><span class="sxs-lookup"><span data-stu-id="55747-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="55747-283">Ссылки на компоненты записи</span><span class="sxs-lookup"><span data-stu-id="55747-283">Capture component references</span></span>

<span data-ttu-id="55747-284">В ASP.NET Web Forms можно управлять экземпляром элемента управления непосредственно в коде, ссылаясь на его идентификатор.</span><span class="sxs-lookup"><span data-stu-id="55747-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="55747-285">В Блазор также можно захватить ссылку на компонент и управлять ей, хотя он гораздо менее распространен.</span><span class="sxs-lookup"><span data-stu-id="55747-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="55747-286">Чтобы записать ссылку на компонент в Блазор, используйте атрибут директивы `@ref`.</span><span class="sxs-lookup"><span data-stu-id="55747-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="55747-287">Значение атрибута должно совпадать с именем настраиваемого поля, имеющего тот же тип, что и компонент, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="55747-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="55747-288">При подготовке к просмотру родительского компонента поле заполняется экземпляром дочернего компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="55747-289">Затем можно вызывать методы в экземпляре компонента или иным образом манипулировать им.</span><span class="sxs-lookup"><span data-stu-id="55747-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="55747-290">Не рекомендуется манипулировать состоянием компонента непосредственно с помощью ссылок на компоненты.</span><span class="sxs-lookup"><span data-stu-id="55747-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="55747-291">Это предотвращает автоматическое отображение компонента в нужное время.</span><span class="sxs-lookup"><span data-stu-id="55747-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="55747-292">Запись ссылок на элементы</span><span class="sxs-lookup"><span data-stu-id="55747-292">Capture element references</span></span>

<span data-ttu-id="55747-293">Компоненты блазор могут записывать ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="55747-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="55747-294">В отличие от серверных элементов управления HTML в веб-формах ASP.NET, модель DOM нельзя манипулировать напрямую с помощью ссылки на элемент в Блазор.</span><span class="sxs-lookup"><span data-stu-id="55747-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="55747-295">Блазор обрабатывает большинство взаимодействий DOM с помощью алгоритма сравнения DOM.</span><span class="sxs-lookup"><span data-stu-id="55747-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="55747-296">Захваченные ссылки на элементы в Блазор являются непрозрачными.</span><span class="sxs-lookup"><span data-stu-id="55747-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="55747-297">Однако они используются для передачи определенной ссылки на элемент в вызове взаимодействия JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55747-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="55747-298">Дополнительные сведения о взаимодействии JavaScript см. в разделе [ASP.NET Core Блазор JavaScript Interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="55747-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="55747-299">Шаблонные компоненты</span><span class="sxs-lookup"><span data-stu-id="55747-299">Templated components</span></span>

<span data-ttu-id="55747-300">В ASP.NET Web Forms можно создавать *шаблонные элементы управления*.</span><span class="sxs-lookup"><span data-stu-id="55747-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="55747-301">Шаблонные элементы управления позволяют разработчику указать часть HTML-кода, используемую для визуализации элемента управления контейнера.</span><span class="sxs-lookup"><span data-stu-id="55747-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="55747-302">Механизм создания шаблонных серверных элементов управления является сложным, но он позволяет создавать эффективные сценарии для отрисовки данных с настраиваемым пользователем способом.</span><span class="sxs-lookup"><span data-stu-id="55747-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="55747-303">Примеры элементов управления с шаблонами включают `Repeater` и `DataList`.</span><span class="sxs-lookup"><span data-stu-id="55747-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="55747-304">Компоненты блазор также можно шаблонировать путем определения параметров компонентов типа `RenderFragment` или `RenderFragment<T>`.</span><span class="sxs-lookup"><span data-stu-id="55747-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="55747-305">`RenderFragment` представляет фрагмент разметки Razor, который затем может быть визуализирован компонентом.</span><span class="sxs-lookup"><span data-stu-id="55747-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="55747-306">`RenderFragment<T>` — это фрагмент разметки Razor, принимающий параметр, который можно указать при подготовке к просмотру фрагмента прорисовки.</span><span class="sxs-lookup"><span data-stu-id="55747-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="55747-307">Дочернее содержимое</span><span class="sxs-lookup"><span data-stu-id="55747-307">Child content</span></span>

<span data-ttu-id="55747-308">Компоненты блазор могут записывать свое дочернее содержимое в виде `RenderFragment` и отображать его в процессе подготовки к просмотру компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="55747-309">Чтобы записать дочернее содержимое, определите параметр компонента типа `RenderFragment` и присвойте ему имя `ChildContent`.</span><span class="sxs-lookup"><span data-stu-id="55747-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="55747-310">*Чилдконтенткомпонент. Razor*</span><span class="sxs-lookup"><span data-stu-id="55747-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="55747-311">После этого родительский компонент может предоставить дочернее содержимое, используя обычные синтаксис Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="55747-312">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="55747-312">Template parameters</span></span>

<span data-ttu-id="55747-313">Шаблонный компонент Блазор также может определять несколько параметров компонента типа `RenderFragment` или `RenderFragment<T>`.</span><span class="sxs-lookup"><span data-stu-id="55747-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="55747-314">Параметр для `RenderFragment<T>` можно указать при его вызове.</span><span class="sxs-lookup"><span data-stu-id="55747-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="55747-315">Чтобы указать параметр универсального типа для компонента, используйте директиву `@typeparam` Razor.</span><span class="sxs-lookup"><span data-stu-id="55747-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="55747-316">*Симплелиствиев. Razor*</span><span class="sxs-lookup"><span data-stu-id="55747-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="55747-317">При использовании компонента шаблона можно указать параметры шаблона с помощью дочерних элементов, соответствующих именам параметров.</span><span class="sxs-lookup"><span data-stu-id="55747-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="55747-318">Аргументы компонента типа `RenderFragment<T>` переданные как элементы, имеют неявный параметр с именем `context`.</span><span class="sxs-lookup"><span data-stu-id="55747-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="55747-319">Имя этого параметра реализации можно изменить с помощью атрибута `Context` дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="55747-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="55747-320">Любые параметры универсального типа можно указать с помощью атрибута, совпадающего с именем параметра типа.</span><span class="sxs-lookup"><span data-stu-id="55747-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="55747-321">Параметр типа будет выведен, если это возможно:</span><span class="sxs-lookup"><span data-stu-id="55747-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="55747-322">Выходные данные этого компонента выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="55747-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="55747-323">Код программной части</span><span class="sxs-lookup"><span data-stu-id="55747-323">Code-behind</span></span>

<span data-ttu-id="55747-324">Компонент Блазор обычно создается в одном файле *Razor* .</span><span class="sxs-lookup"><span data-stu-id="55747-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="55747-325">Однако можно разделить код и разметку с помощью файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="55747-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="55747-326">Чтобы использовать файл компонента, добавьте C# файл, соответствующий имени файла компонента, но с добавленным расширением *CS* (*Counter.Razor.CS*).</span><span class="sxs-lookup"><span data-stu-id="55747-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="55747-327">Используйте C# файл, чтобы определить базовый класс для компонента.</span><span class="sxs-lookup"><span data-stu-id="55747-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="55747-328">Можно присвоить имя базовому классу все, что вам нужно, но обычно имя класса является таким же, как и класс Component, но с добавленным расширением `Base` (`CounterBase`).</span><span class="sxs-lookup"><span data-stu-id="55747-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="55747-329">Класс на основе компонентов также должен быть производным от `ComponentBase`.</span><span class="sxs-lookup"><span data-stu-id="55747-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="55747-330">Затем в файле компонента Razor добавьте директиву `@inherits`, чтобы указать базовый класс для компонента (`@inherits CounterBase`).</span><span class="sxs-lookup"><span data-stu-id="55747-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="55747-331">*Счетчик. Razor*</span><span class="sxs-lookup"><span data-stu-id="55747-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="55747-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="55747-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="55747-333">Видимость членов компонента в базовом классе должна быть `protected` или `public`, чтобы быть видимыми для класса Component.</span><span class="sxs-lookup"><span data-stu-id="55747-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55747-334">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="55747-334">Additional resources</span></span>

<span data-ttu-id="55747-335">Предыдущая не является исчерпывающей облечения всех аспектов компонентов Блазор.</span><span class="sxs-lookup"><span data-stu-id="55747-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="55747-336">Дополнительные сведения о [создании и использовании ASP.NET Core компонентов Razor](/aspnet/core/blazor/components)см. в документации по блазор.</span><span class="sxs-lookup"><span data-stu-id="55747-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="55747-337">[Назад](app-startup.md)
>[Вперед](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="55747-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
