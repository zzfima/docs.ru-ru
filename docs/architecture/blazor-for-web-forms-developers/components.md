---
title: Создание многоразовых компонентов uI с помощью Blazor
description: Узнайте, как создавать многоразовые компоненты uI с помощью Blazor и как они соотносятся с ASP.NET элементами управления веб-формами.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228626"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="e2ffb-103">Создание многоразовых компонентов uI с помощью Blazor</span><span class="sxs-lookup"><span data-stu-id="e2ffb-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e2ffb-104">Одна из красивых вещей о ASP.NET Web Forms, как она позволяет инкапсуляции многоразовых частей пользовательского интерфейса (UI) код в многоразовые элементы управления пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="e2ffb-105">Пользовательские элементы управления пользователем могут быть определены в разметке с помощью файлов *.ascx.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="e2ffb-106">Вы также можете создать сложные элементы управления сервером в коде с полной поддержкой конструктора.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="e2ffb-107">Blazor также поддерживает инкапсуляцию uI через *компоненты.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="e2ffb-108">Компонент:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-108">A component:</span></span>

- <span data-ttu-id="e2ffb-109">Является автономным фрагментом uI.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="e2ffb-110">Сохраняет свое состояние и логику рендеринга.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="e2ffb-111">Можно определить обработчики событий, привязать к входным данным и управлять собственным жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="e2ffb-112">Обычно определяется в файле *.razor* с помощью синтаксиса Razor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="e2ffb-113">Введение в Razor</span><span class="sxs-lookup"><span data-stu-id="e2ffb-113">An introduction to Razor</span></span>

<span data-ttu-id="e2ffb-114">Razor — это легкий язык шаблонов, основанный на HTML и C.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="e2ffb-115">С помощью Razor можно плавно переходить между разметкой и кодом C-кода для определения логики визуализации компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="e2ffb-116">При компилировании *файла .razor* логика визуализации фиксируется структурированным образом в классе .NET.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="e2ffb-117">Название скомпилированного класса взято из имени *файла .razor.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="e2ffb-118">Пространство имен взято из пространства имен по умолчанию для проекта и пути папки, `@namespace` или вы можете явно указать пространство имен с помощью директивы (подробнее о директивах Razor ниже).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="e2ffb-119">Логика визуализации компонента написана с использованием обычной HTML-разметки с динамической логикой, добавленной с помощью C.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="e2ffb-120">Персонаж `@` используется для перехода на C.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="e2ffb-121">Razor, как правило, умные о выяснении, когда вы перешли обратно в HTML.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="e2ffb-122">Например, следующий компонент `<p>` отображает тег с текущим временем:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="e2ffb-123">Чтобы четко указать начало и окончание выражения C, используйте скобки:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="e2ffb-124">Razor также упрощает использование потока управления C's в логике рендеринга.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="e2ffb-125">Например, можно условно визуализировать некоторые HTML следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="e2ffb-126">Или вы можете создать список элементов, используя обычный цикл C's `foreach` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="e2ffb-127">Директивы Razor, такие как директивы в ASP.NET веб-формах, контролируют многие аспекты компиляции компонента Razor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="e2ffb-128">Примеры включают компонент:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-128">Examples include the component's:</span></span>

- <span data-ttu-id="e2ffb-129">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e2ffb-129">Namespace</span></span>
- <span data-ttu-id="e2ffb-130">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="e2ffb-130">Base class</span></span>
- <span data-ttu-id="e2ffb-131">Реализованные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e2ffb-131">Implemented interfaces</span></span>
- <span data-ttu-id="e2ffb-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e2ffb-132">Generic parameters</span></span>
- <span data-ttu-id="e2ffb-133">Импортированные пространства имен</span><span class="sxs-lookup"><span data-stu-id="e2ffb-133">Imported namespaces</span></span>
- <span data-ttu-id="e2ffb-134">Маршруты</span><span class="sxs-lookup"><span data-stu-id="e2ffb-134">Routes</span></span>

<span data-ttu-id="e2ffb-135">Директивы Razor начинаются с символа `@` и обычно используются в начале новой строки в начале файла.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="e2ffb-136">Например, `@namespace` директива определяет пространство имен компонента:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="e2ffb-137">В следующей таблице кратко излагаются различные директивы Razor, используемые в Blazor и их эквиваленты ASP.NET Web-форм, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="e2ffb-138">Директива</span><span class="sxs-lookup"><span data-stu-id="e2ffb-138">Directive</span></span>    |<span data-ttu-id="e2ffb-139">Описание</span><span class="sxs-lookup"><span data-stu-id="e2ffb-139">Description</span></span>|<span data-ttu-id="e2ffb-140">Пример</span><span class="sxs-lookup"><span data-stu-id="e2ffb-140">Example</span></span>|<span data-ttu-id="e2ffb-141">Эквивалент веб-форм</span><span class="sxs-lookup"><span data-stu-id="e2ffb-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="e2ffb-142">Добавляет атрибут уровня класса к компоненту</span><span class="sxs-lookup"><span data-stu-id="e2ffb-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="e2ffb-143">None</span><span class="sxs-lookup"><span data-stu-id="e2ffb-143">None</span></span>|
|`@code`      |<span data-ttu-id="e2ffb-144">Добавляет членов класса к компоненту</span><span class="sxs-lookup"><span data-stu-id="e2ffb-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="e2ffb-145">Реализует указанный интерфейс</span><span class="sxs-lookup"><span data-stu-id="e2ffb-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="e2ffb-146">Использование кода программной части</span><span class="sxs-lookup"><span data-stu-id="e2ffb-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="e2ffb-147">Наследует от указанного базового класса</span><span class="sxs-lookup"><span data-stu-id="e2ffb-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="e2ffb-148">Впрыскивает услугу в компонент</span><span class="sxs-lookup"><span data-stu-id="e2ffb-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="e2ffb-149">None</span><span class="sxs-lookup"><span data-stu-id="e2ffb-149">None</span></span>|
|`@layout`    |<span data-ttu-id="e2ffb-150">Определяет компонент макета для компонента</span><span class="sxs-lookup"><span data-stu-id="e2ffb-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="e2ffb-151">Устанавливает пространство имен для компонента</span><span class="sxs-lookup"><span data-stu-id="e2ffb-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="e2ffb-152">None</span><span class="sxs-lookup"><span data-stu-id="e2ffb-152">None</span></span>|
|`@page`      |<span data-ttu-id="e2ffb-153">Определяет маршрут для компонента</span><span class="sxs-lookup"><span data-stu-id="e2ffb-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="e2ffb-154">Определяет общий параметр типа для компонента</span><span class="sxs-lookup"><span data-stu-id="e2ffb-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="e2ffb-155">Использование кода программной части</span><span class="sxs-lookup"><span data-stu-id="e2ffb-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="e2ffb-156">Определяет пространство имен для вхобряда</span><span class="sxs-lookup"><span data-stu-id="e2ffb-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="e2ffb-157">Добавление пространства имен в *web.config*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="e2ffb-158">Компоненты Razor также широко используют *директивные атрибуты* на элементах для контроля различных аспектов компилируется компонентов (обработка событий, привязка данных, ссылки на компоненты & элементов и так далее).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="e2ffb-159">Директивные атрибуты следуют общему общему синтаксису, где значения в скобках неявляются:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="e2ffb-160">В следующей таблице кратко излагаются различные атрибуты для директив Razor, используемых в Blazor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="e2ffb-161">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2ffb-161">Attribute</span></span>    |<span data-ttu-id="e2ffb-162">Описание</span><span class="sxs-lookup"><span data-stu-id="e2ffb-162">Description</span></span>|<span data-ttu-id="e2ffb-163">Пример</span><span class="sxs-lookup"><span data-stu-id="e2ffb-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="e2ffb-164">Рендерс словарь атрибутов</span><span class="sxs-lookup"><span data-stu-id="e2ffb-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="e2ffb-165">Создает двусторонняя привязка данных</span><span class="sxs-lookup"><span data-stu-id="e2ffb-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="e2ffb-166">Добавлен обработчик события для указанного события</span><span class="sxs-lookup"><span data-stu-id="e2ffb-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="e2ffb-167">Определяет ключ, который будет использоваться алгоритмом рассеивания для сохранения элементов в коллекции</span><span class="sxs-lookup"><span data-stu-id="e2ffb-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="e2ffb-168">Захватывает ссылку на компонент или HTML-элемент</span><span class="sxs-lookup"><span data-stu-id="e2ffb-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="e2ffb-169">Различные атрибуты директивы,`@onclick`используемые `@ref`Blazor (, `@bind`и так далее), описаны в разделах ниже и в более поздних главах.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="e2ffb-170">Многие синтаксисы, используемые в *файлах .aspx* и *.ascx,* имеют параллельные синтаксисы в Razor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="e2ffb-171">Ниже приводится простое сравнение синтаксисов для ASP.NET веб-форм и бритвы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="e2ffb-172">Компонент</span><span class="sxs-lookup"><span data-stu-id="e2ffb-172">Feature</span></span>                      |<span data-ttu-id="e2ffb-173">Веб-формы</span><span class="sxs-lookup"><span data-stu-id="e2ffb-173">Web Forms</span></span>           |<span data-ttu-id="e2ffb-174">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2ffb-174">Syntax</span></span>               |<span data-ttu-id="e2ffb-175">Razor</span><span class="sxs-lookup"><span data-stu-id="e2ffb-175">Razor</span></span>         |<span data-ttu-id="e2ffb-176">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2ffb-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="e2ffb-177">Директивы</span><span class="sxs-lookup"><span data-stu-id="e2ffb-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="e2ffb-178">Блоки кода</span><span class="sxs-lookup"><span data-stu-id="e2ffb-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="e2ffb-179">Выражения</span><span class="sxs-lookup"><span data-stu-id="e2ffb-179">Expressions</span></span><br><span data-ttu-id="e2ffb-180">(HTML-кодированный)</span><span class="sxs-lookup"><span data-stu-id="e2ffb-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="e2ffb-181">Неявные:`@`</span><span class="sxs-lookup"><span data-stu-id="e2ffb-181">Implicit: `@`</span></span><br><span data-ttu-id="e2ffb-182">Явные:`@()`</span><span class="sxs-lookup"><span data-stu-id="e2ffb-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="e2ffb-183">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e2ffb-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="e2ffb-184">привязка данных,</span><span class="sxs-lookup"><span data-stu-id="e2ffb-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="e2ffb-185">Чтобы добавить участников в класс `@code` компонента Razor, используйте директиву.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="e2ffb-186">Этот метод аналогичен `<script runat="server">...</script>` использованию блока в ASP.NET веб-формы управления пользователем или страницы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="e2ffb-187">Так как Razor основан на C, она должна быть составлена в рамках проекта C ' (*.csproj*).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="e2ffb-188">Вы не можете компилировать *файлы .razor* из проекта Visual Basic *(.vbproj*).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="e2ffb-189">Вы все еще можете ссылаться на проекты Visual Basic из вашего проекта Blazor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="e2ffb-190">Обратное верно тоже.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-190">The opposite is true too.</span></span>

<span data-ttu-id="e2ffb-191">Для полной ссылки синтаксиса Razor см. [ссылку на синтаксис Razor для ASP.NET Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="e2ffb-192">Использование компонентов</span><span class="sxs-lookup"><span data-stu-id="e2ffb-192">Use components</span></span>

<span data-ttu-id="e2ffb-193">Помимо обычного HTML, компоненты могут также использовать другие компоненты как часть их логики рендеринга.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="e2ffb-194">Синтаксис для использования компонента в Razor аналогичен использованию управления пользователем в ASP.NET web Forms.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="e2ffb-195">Компоненты уогоняются с помощью тега элемента, который соответствует имени типа компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="e2ffb-196">Например, можно добавить `Counter` такой компонент:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="e2ffb-197">В отличие от ASP.NET веб-форм, компоненты в Blazor:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="e2ffb-198">Не используйте префикс элемента `asp:`(например, ).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="e2ffb-199">Не требуется регистрация на странице или в *веб.сайте.config*.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="e2ffb-200">Подумайте о компонентах Razor, как вы бы .NET типов, потому что это именно то, что они есть.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="e2ffb-201">Если на сборку, содержащую компонент, ссылаются, то компонент доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="e2ffb-202">Чтобы привести пространство имен компонента в `@using` сферу применения директивы:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="e2ffb-203">Как видно из проектов Blazor по умолчанию, обычно директивы помещаются `@using` в файл *_Imports.razor,* чтобы они импортировались во все файлы *.razor* в одном каталоге и в каталогах детей.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="e2ffb-204">Если пространство имен для компонента не входит в сферу действия, можно указать компонент, используя его полное имя типа, как это возможно в C:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="e2ffb-205">Параметры компонентов</span><span class="sxs-lookup"><span data-stu-id="e2ffb-205">Component parameters</span></span>

<span data-ttu-id="e2ffb-206">В ASP.NET web-формах можно передавать параметры и данные в элементы управления с использованием общедоступных свойств.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="e2ffb-207">Эти свойства можно установить в разметке с помощью атрибутов или установить непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="e2ffb-208">Компоненты Blazor работают аналогичным образом, хотя свойства компонента также должны быть помечены `[Parameter]` атрибутом, который должен рассматриваться как параметры компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="e2ffb-209">Следующий `Counter` компонент определяет параметр `IncrementAmount` компонента, который может быть `Counter` использован для определения суммы, которую необходимо приравливать при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="e2ffb-210">Чтобы указать параметр компонента в Blazor, используйте атрибут, как вы бы в ASP.NET веб-формы:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="e2ffb-211">Обработчики событий</span><span class="sxs-lookup"><span data-stu-id="e2ffb-211">Event handlers</span></span>

<span data-ttu-id="e2ffb-212">Как ASP.NET Web Forms, так и Blazor обеспечивают модель программирования на основе событий для обработки событий uI.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="e2ffb-213">Примеры таких событий включают нажатия кликов и ввод текста.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="e2ffb-214">В ASP.NET Web Forms вы используете элементы управления HTML-сервера для обработки событий uI, подвергаемых DOM, или можете обрабатывать события, подвергающиеся воздействию элементов управления веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="e2ffb-215">События всплывают на сервере через запросы формы после возврата.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="e2ffb-216">Рассмотрим следующий пример кнопки Web Forms нажмите кнопку:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="e2ffb-217">*Counter.ascx*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="e2ffb-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="e2ffb-219">В Blazor можно регистрировать обработчики событий DOM UI `@on{event}`напрямую с помощью директивных атрибутов формы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="e2ffb-220">Заполнитель `{event}` представляет название события.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="e2ffb-221">Например, вы можете слушать кнопки кликов, как это:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="e2ffb-222">Обработчики событий могут принять дополнительный аргумент, конкретный для конкретных событий, чтобы предоставить более подробную информацию о событии.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="e2ffb-223">Например, события мыши `MouseEventArgs` могут быть аргументом, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="e2ffb-224">Вместо того, чтобы ссылаться на группу метода для обработчика событий, можно использовать выражение лямбда.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="e2ffb-225">Выражение lambda позволяет закрыть по сравнению с другими значениями в области.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="e2ffb-226">Обработчики событий могут выполняться синхронно или синхронно.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="e2ffb-227">Например, обработчик событий выполняет `OnClick` асинхронно:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="e2ffb-228">После обработки события компонент отображается для учета любых изменений состояния компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="e2ffb-229">С помощью асинхронных обработчиков событий компонент отображается сразу после завершения выполнения обработчика.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="e2ffb-230">Компонент визуалируется *снова* после `Task` асинхронного завершения.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="e2ffb-231">Этот асинхронный режим выполнения предоставляет возможность рендеринга некоторого `Task` соответствующего uI, пока асинхронный еще продолжается.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

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

<span data-ttu-id="e2ffb-232">Компоненты могут также определять свои собственные события, определяя параметр компонента типа. `EventCallback<TValue>`</span><span class="sxs-lookup"><span data-stu-id="e2ffb-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="e2ffb-233">Обратные вызовы событий поддерживают все вариации обработчиков событий DOM UI: дополнительные аргументы, синхронные или асинхронные, группы методов или выражения лямбды.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="e2ffb-234">привязка данных,</span><span class="sxs-lookup"><span data-stu-id="e2ffb-234">Data binding</span></span>

<span data-ttu-id="e2ffb-235">Blazor предоставляет простой механизм привязывания данных из компонента uI в состояние компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="e2ffb-236">Этот подход отличается от функций в ASP.NET Web-форм для связывания данных от источников данных к элементам управления uI.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="e2ffb-237">Мы рассмотрим обработку данных из различных источников данных в разделе [Dealing with data.](data.md)</span><span class="sxs-lookup"><span data-stu-id="e2ffb-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="e2ffb-238">Чтобы создать двусторонню привязку данных от компонента uI `@bind` к состоянию компонента, используйте атрибут директивы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="e2ffb-239">В следующем примере значение флажка привязано `isChecked` к полю.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="e2ffb-240">При визуализации компонент устанавливается значение флажка к значению `isChecked` поля.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="e2ffb-241">Когда пользователь переключает флажок, `onchange` событие сражается и `isChecked` поле настроено на новое значение.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="e2ffb-242">Синтаксис `@bind` в данном случае эквивалентен следующей разметке:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="e2ffb-243">Чтобы изменить событие, используемое для `@bind:event` связывания, используйте атрибут.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="e2ffb-244">Компоненты также могут поддерживать привязку данных к их параметрам.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="e2ffb-245">Для связывания данных определите параметр обратного вызова события с тем же именем, что и параметр bindable.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="e2ffb-246">К названию добавляется суффикс "Измененный".</span><span class="sxs-lookup"><span data-stu-id="e2ffb-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="e2ffb-247">*PasswordBox.razor*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="e2ffb-248">Чтобы сгваить привязку данных к базовому элементу uI, установите `@bind` значение и обгоните событие непосредственно на элементе uI вместо использования атрибута.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="e2ffb-249">Чтобы привязаться к параметру компонента, используйте `@bind-{Parameter}` атрибут, чтобы указать параметр, к которому вы хотите привязать.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="e2ffb-250">Изменения состояний</span><span class="sxs-lookup"><span data-stu-id="e2ffb-250">State changes</span></span>

<span data-ttu-id="e2ffb-251">Если состояние компонента изменилось за пределами обычного события или обратного вызова события, то компонент должен вручную сигнализировать о необходимости повторного отображаемого.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="e2ffb-252">Чтобы сигнализировать об изменении состояния `StateHasChanged` компонента, позвоните в метод на компоненте.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="e2ffb-253">В приведенном ниже примере компонент отображает `AppState` сообщение из службы, которое может быть обновлено другими частями приложения.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="e2ffb-254">Компонент регистрирует свой `StateHasChanged` метод `AppState.OnChange` с событием, чтобы компонент визуализировался всякий раз, когда сообщение обновляется.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

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

## <a name="component-lifecycle"></a><span data-ttu-id="e2ffb-255">Цикл жизни компонентов</span><span class="sxs-lookup"><span data-stu-id="e2ffb-255">Component lifecycle</span></span>

<span data-ttu-id="e2ffb-256">В рамках ASP.NET Web Forms есть четко определенные методы жизненного цикла для модулей, страниц и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="e2ffb-257">Например, следующий элемент управления реализует `Init`обработчики событий для событий , `Load`и `UnLoad` жизненного цикла:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="e2ffb-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="e2ffb-259">Компоненты Blazor также имеют четко определенный жизненный цикл.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="e2ffb-260">Жизненный цикл компонента может быть использован для инициализации состояния компонентов и реализации передовых поведения компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="e2ffb-261">Все методы жизненного цикла компонентов Blazor имеют как синхронные, так и асинхронные версии.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="e2ffb-262">Компонентная визуализация синхронна.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-262">Component rendering is synchronous.</span></span> <span data-ttu-id="e2ffb-263">Нельзя запускать асинхронную логику как часть рендеринга компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="e2ffb-264">Вся асинхронная логика `async` должна выполняться как часть метода жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="e2ffb-265">На Первоначальный</span><span class="sxs-lookup"><span data-stu-id="e2ffb-265">OnInitialized</span></span>

<span data-ttu-id="e2ffb-266">`OnInitialized` Методы `OnInitializedAsync` и методы используются для инициализации компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="e2ffb-267">Компонент обычно инициализируется после его первой визуализации.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="e2ffb-268">После того, как компонент инициализирован, он может быть отрисован несколько раз, прежде чем он в конечном итоге удаляется.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="e2ffb-269">Метод `OnInitialized` аналогичен `Page_Load` событию в ASP.NET веб-форм страниц и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="e2ffb-270">На ПаразамносSet</span><span class="sxs-lookup"><span data-stu-id="e2ffb-270">OnParametersSet</span></span>

<span data-ttu-id="e2ffb-271">`OnParametersSet` Методы `OnParametersSetAsync` и методы вызываются, когда компонент получил параметры от своего родителя и значение присваивается свойствам.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="e2ffb-272">Эти методы выполняются после инициализации компонента и *каждый раз, когда компонент визуализироваться.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="e2ffb-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="e2ffb-273">OnAfterRender</span></span>

<span data-ttu-id="e2ffb-274">`OnAfterRender` Методы `OnAfterRenderAsync` и методы называются после завершения рендеринга компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="e2ffb-275">На данный момент населяются ссылки элементов и компонентов (подробнее об этих понятиях ниже).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="e2ffb-276">Интерактивная активность с браузером включена в этой точке.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="e2ffb-277">Взаимодействие с выполнением DOM и JavaScript может безопасно.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="e2ffb-278">`OnAfterRender`и `OnAfterRenderAsync` *не называются при предварительной рендеринге на сервере.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="e2ffb-279">Параметр `firstRender` `true` — это первый раз, когда компонент визуализироваться; в противном `false`случае, его значение .</span><span class="sxs-lookup"><span data-stu-id="e2ffb-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="e2ffb-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="e2ffb-280">IDisposable</span></span>

<span data-ttu-id="e2ffb-281">Компоненты Blazor `IDisposable` могут осуществляться для удаления ресурсов при удалении компонента из uI.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="e2ffb-282">Компонент Razor может `IDispose` реализовать `@implements` с помощью директивы:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="e2ffb-283">Ссылки на компонент захвата</span><span class="sxs-lookup"><span data-stu-id="e2ffb-283">Capture component references</span></span>

<span data-ttu-id="e2ffb-284">В ASP.NET Web Forms обычно можно манипулировать экземпляром управления непосредственно в коде, ссылаясь на его идентификатор.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="e2ffb-285">В Blazor также можно запечатлеть и манипулировать ссылкой на компонент, хотя это гораздо реже.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="e2ffb-286">Чтобы зафиксировать ссылку на `@ref` компоненты в Blazor, используйте атрибут директивы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="e2ffb-287">Значение атрибута должно совпадать с именем поля settable с тем же типом, что и ссылки на компонент.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="e2ffb-288">При визуализации родительского компонента поле заполняется экземпляром детского компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="e2ffb-289">Затем можно вызвать методы на примере компонента или иным образом манипулировать иным образом.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="e2ffb-290">Манипулирование состоянием компонента непосредственно с использованием ссылок компонентов не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="e2ffb-291">Это предотвращает автоматический отрисованный компонент в нужное время.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="e2ffb-292">Ссылки элемента захвата</span><span class="sxs-lookup"><span data-stu-id="e2ffb-292">Capture element references</span></span>

<span data-ttu-id="e2ffb-293">Компоненты Blazor могут фиксировать ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="e2ffb-294">В отличие от управления HTML-серверами в ASP.NET Web-форм, вы не можете манипулировать DOM напрямую, используя ссылку на элемент blazor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="e2ffb-295">Blazor обрабатывает большинство взаимодействий DOM для вас, используя алгоритм диффинга DOM.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="e2ffb-296">Ссылки на захваченные элементы в Blazor непрозрачны.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="e2ffb-297">Тем не менее, они используются для передачи определенной ссылки элемента в вызове Interop JavaScript.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="e2ffb-298">Для получения дополнительной информации о JavaScript interop, [см. ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="e2ffb-299">Шаблонные компоненты</span><span class="sxs-lookup"><span data-stu-id="e2ffb-299">Templated components</span></span>

<span data-ttu-id="e2ffb-300">В ASP.NET веб-формах можно создавать *шаблонные элементы управления.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="e2ffb-301">Шаблонные элементы управления позволяют разработчику указать часть HTML, используемую для визуализации управления контейнером.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="e2ffb-302">Механика создания шаблонных элементов управления сервером сложна, но они позволяют мощным сценариям визуализации данных настраиваемым способом.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="e2ffb-303">Примеры шаблонных `Repeater` элементов управления включают и `DataList`.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="e2ffb-304">Компоненты Blazor также можно шаблонировать путем `RenderFragment` `RenderFragment<T>`определения параметров компонентов типа или .</span><span class="sxs-lookup"><span data-stu-id="e2ffb-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="e2ffb-305">A `RenderFragment` представляет собой кусок разметки Razor, который затем может быть отрисован компонентом.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="e2ffb-306">A `RenderFragment<T>` — это кусок разметки Razor, который принимает параметр, который может быть указан при визуализации фрагмента визы.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="e2ffb-307">Детский контент</span><span class="sxs-lookup"><span data-stu-id="e2ffb-307">Child content</span></span>

<span data-ttu-id="e2ffb-308">Компоненты Blazor могут отображать `RenderFragment` содержимое своего ребенка как содержимое и отображать его как часть рендеринга компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="e2ffb-309">Чтобы захватить содержимое ребенка, `RenderFragment` определите `ChildContent`параметр компонента типа и назовите его.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="e2ffb-310">*ChildContentComponent.razor*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="e2ffb-311">Родительский компонент может поставлять содержимое ребенка с помощью обычного синтаксиса Razor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="e2ffb-312">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="e2ffb-312">Template parameters</span></span>

<span data-ttu-id="e2ffb-313">Шаблонированный компонент Blazor может также определить `RenderFragment` несколько параметров компонента типа или. `RenderFragment<T>`</span><span class="sxs-lookup"><span data-stu-id="e2ffb-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="e2ffb-314">Параметр для `RenderFragment<T>` можно указать при вызове.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="e2ffb-315">Чтобы указать общий параметр типа `@typeparam` для компонента, используйте директиву Razor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="e2ffb-316">*SimpleListView.razor*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="e2ffb-317">При использовании шаблонного компонента параметры шаблона могут быть указаны с помощью элементов детского использования, которые соответствуют названиям параметров.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="e2ffb-318">Компонентные аргументы `RenderFragment<T>` типа, пройденные `context`как элементы, имеют неявный параметр под названием.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="e2ffb-319">Можно изменить имя параметра реализации `Context` с помощью атрибута на элементе ребенка.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="e2ffb-320">Любые параметры общего типа могут быть указаны с помощью атрибута, который соответствует названию параметра типа.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="e2ffb-321">Параметр типа будет выведен, если это возможно:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-321">The type parameter will be inferred if possible:</span></span>

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

<span data-ttu-id="e2ffb-322">Выход этого компонента выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2ffb-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="e2ffb-323">Файл с кодом программной части</span><span class="sxs-lookup"><span data-stu-id="e2ffb-323">Code-behind</span></span>

<span data-ttu-id="e2ffb-324">Компонент Blazor обычно авторизуется в одном файле *.razor.*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="e2ffb-325">Тем не менее, можно также разделить код и разметку с помощью файла с кодом.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="e2ffb-326">Чтобы использовать файл компонента, добавьте файл C,s, который соответствует названию файла компонента, но с добавлением *расширения .cs* *(Counter.razor.cs).*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="e2ffb-327">Используйте файл C-класса для определения базового класса для компонента.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="e2ffb-328">Вы можете назвать базовый класс все, что вы хотите, но это общее имя класса `Base` так же, как компонент класса, но с расширением добавил (`CounterBase`).</span><span class="sxs-lookup"><span data-stu-id="e2ffb-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="e2ffb-329">Класс, основанный на компонентах, также должен быть получен из `ComponentBase`.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="e2ffb-330">Затем, в файл компонента Razor, добавьте директиву, `@inherits` `@inherits CounterBase`чтобы указать базовый класс для компонента ().</span><span class="sxs-lookup"><span data-stu-id="e2ffb-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="e2ffb-331">*Counter.razor*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="e2ffb-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="e2ffb-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="e2ffb-333">Видимость членов компонента в базовом классе `protected` должна `public` быть или быть видимой для класса компонентов.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e2ffb-334">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e2ffb-334">Additional resources</span></span>

<span data-ttu-id="e2ffb-335">Предыдущее не является исчерпывающим обращением ко всем аспектам компонентов Blazor.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="e2ffb-336">Для получения дополнительной информации о том, как [создавать и использовать ASP.NET компоненты Core Razor,](/aspnet/core/blazor/components)см.</span><span class="sxs-lookup"><span data-stu-id="e2ffb-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e2ffb-337">[Предыдущий](app-startup.md)
>[Следующий](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="e2ffb-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
