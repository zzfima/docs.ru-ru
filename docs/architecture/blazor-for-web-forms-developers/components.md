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
# <a name="build-reusable-ui-components-with-blazor"></a>Создание многоразовых компонентов uI с помощью Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Одна из красивых вещей о ASP.NET Web Forms, как она позволяет инкапсуляции многоразовых частей пользовательского интерфейса (UI) код в многоразовые элементы управления пользовательского интерфейса. Пользовательские элементы управления пользователем могут быть определены в разметке с помощью файлов *.ascx.* Вы также можете создать сложные элементы управления сервером в коде с полной поддержкой конструктора.

Blazor также поддерживает инкапсуляцию uI через *компоненты.* Компонент:

- Является автономным фрагментом uI.
- Сохраняет свое состояние и логику рендеринга.
- Можно определить обработчики событий, привязать к входным данным и управлять собственным жизненным циклом.
- Обычно определяется в файле *.razor* с помощью синтаксиса Razor.

## <a name="an-introduction-to-razor"></a>Введение в Razor

Razor — это легкий язык шаблонов, основанный на HTML и C. С помощью Razor можно плавно переходить между разметкой и кодом C-кода для определения логики визуализации компонентов. При компилировании *файла .razor* логика визуализации фиксируется структурированным образом в классе .NET. Название скомпилированного класса взято из имени *файла .razor.* Пространство имен взято из пространства имен по умолчанию для проекта и пути папки, `@namespace` или вы можете явно указать пространство имен с помощью директивы (подробнее о директивах Razor ниже).

Логика визуализации компонента написана с использованием обычной HTML-разметки с динамической логикой, добавленной с помощью C. Персонаж `@` используется для перехода на C. Razor, как правило, умные о выяснении, когда вы перешли обратно в HTML. Например, следующий компонент `<p>` отображает тег с текущим временем:

```razor
<p>@DateTime.Now</p>
```

Чтобы четко указать начало и окончание выражения C, используйте скобки:

```razor
<p>@(DateTime.Now)</p>
```

Razor также упрощает использование потока управления C's в логике рендеринга. Например, можно условно визуализировать некоторые HTML следующим образом:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

Или вы можете создать список элементов, используя обычный цикл C's `foreach` следующим образом:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Директивы Razor, такие как директивы в ASP.NET веб-формах, контролируют многие аспекты компиляции компонента Razor. Примеры включают компонент:

- Пространство имен
- Базовый класс
- Реализованные интерфейсы
- Общие параметры
- Импортированные пространства имен
- Маршруты

Директивы Razor начинаются с символа `@` и обычно используются в начале новой строки в начале файла. Например, `@namespace` директива определяет пространство имен компонента:

```razor
@namespace MyComponentNamespace
```

В следующей таблице кратко излагаются различные директивы Razor, используемые в Blazor и их эквиваленты ASP.NET Web-форм, если они существуют.

|Директива    |Описание|Пример|Эквивалент веб-форм|
|-------------|-----------|-------|--------------------|
|`@attribute` |Добавляет атрибут уровня класса к компоненту|`@attribute [Authorize]`|None|
|`@code`      |Добавляет членов класса к компоненту|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Реализует указанный интерфейс|`@implements IDisposable`|Использование кода программной части|
|`@inherits`  |Наследует от указанного базового класса|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Впрыскивает услугу в компонент|`@inject IJSRuntime JS`|None|
|`@layout`    |Определяет компонент макета для компонента|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Устанавливает пространство имен для компонента|`@namespace MyNamespace`|None|
|`@page`      |Определяет маршрут для компонента|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Определяет общий параметр типа для компонента|`@typeparam TItem`|Использование кода программной части|
|`@using`     |Определяет пространство имен для вхобряда|`@using MyComponentNamespace`|Добавление пространства имен в *web.config*|

Компоненты Razor также широко используют *директивные атрибуты* на элементах для контроля различных аспектов компилируется компонентов (обработка событий, привязка данных, ссылки на компоненты & элементов и так далее). Директивные атрибуты следуют общему общему синтаксису, где значения в скобках неявляются:

```razor
@directive(-suffix(:name))(="value")
```

В следующей таблице кратко излагаются различные атрибуты для директив Razor, используемых в Blazor.

|Атрибут    |Описание|Пример|
|-------------|-----------|-------|
|`@attributes`|Рендерс словарь атрибутов|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Создает двусторонняя привязка данных    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Добавлен обработчик события для указанного события|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Определяет ключ, который будет использоваться алгоритмом рассеивания для сохранения элементов в коллекции|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Захватывает ссылку на компонент или HTML-элемент|`<MyDialog @ref="myDialog" />`|

Различные атрибуты директивы,`@onclick`используемые `@ref`Blazor (, `@bind`и так далее), описаны в разделах ниже и в более поздних главах.

Многие синтаксисы, используемые в *файлах .aspx* и *.ascx,* имеют параллельные синтаксисы в Razor. Ниже приводится простое сравнение синтаксисов для ASP.NET веб-форм и бритвы.

|Компонент                      |Веб-формы           |Синтаксис               |Razor         |Синтаксис |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Директивы                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Блоки кода                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Выражения<br>(HTML-кодированный)|`<%: %>`            |`<%:DateTime.Now %>` |Неявные:`@`<br>Явные:`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Комментарии                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|привязка данных,                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Чтобы добавить участников в класс `@code` компонента Razor, используйте директиву. Этот метод аналогичен `<script runat="server">...</script>` использованию блока в ASP.NET веб-формы управления пользователем или страницы.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Так как Razor основан на C, она должна быть составлена в рамках проекта C ' (*.csproj*). Вы не можете компилировать *файлы .razor* из проекта Visual Basic *(.vbproj*). Вы все еще можете ссылаться на проекты Visual Basic из вашего проекта Blazor. Обратное верно тоже.

Для полной ссылки синтаксиса Razor см. [ссылку на синтаксис Razor для ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Использование компонентов

Помимо обычного HTML, компоненты могут также использовать другие компоненты как часть их логики рендеринга. Синтаксис для использования компонента в Razor аналогичен использованию управления пользователем в ASP.NET web Forms. Компоненты уогоняются с помощью тега элемента, который соответствует имени типа компонента. Например, можно добавить `Counter` такой компонент:

```razor
<Counter />
```

В отличие от ASP.NET веб-форм, компоненты в Blazor:

- Не используйте префикс элемента `asp:`(например, ).
- Не требуется регистрация на странице или в *веб.сайте.config*.

Подумайте о компонентах Razor, как вы бы .NET типов, потому что это именно то, что они есть. Если на сборку, содержащую компонент, ссылаются, то компонент доступен для использования. Чтобы привести пространство имен компонента в `@using` сферу применения директивы:

```razor
@using MyComponentLib

<Counter />
```

Как видно из проектов Blazor по умолчанию, обычно директивы помещаются `@using` в файл *_Imports.razor,* чтобы они импортировались во все файлы *.razor* в одном каталоге и в каталогах детей.

Если пространство имен для компонента не входит в сферу действия, можно указать компонент, используя его полное имя типа, как это возможно в C:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Параметры компонентов

В ASP.NET web-формах можно передавать параметры и данные в элементы управления с использованием общедоступных свойств. Эти свойства можно установить в разметке с помощью атрибутов или установить непосредственно в коде. Компоненты Blazor работают аналогичным образом, хотя свойства компонента также должны быть помечены `[Parameter]` атрибутом, который должен рассматриваться как параметры компонентов.

Следующий `Counter` компонент определяет параметр `IncrementAmount` компонента, который может быть `Counter` использован для определения суммы, которую необходимо приравливать при нажатии кнопки.

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

Чтобы указать параметр компонента в Blazor, используйте атрибут, как вы бы в ASP.NET веб-формы:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Обработчики событий

Как ASP.NET Web Forms, так и Blazor обеспечивают модель программирования на основе событий для обработки событий uI. Примеры таких событий включают нажатия кликов и ввод текста. В ASP.NET Web Forms вы используете элементы управления HTML-сервера для обработки событий uI, подвергаемых DOM, или можете обрабатывать события, подвергающиеся воздействию элементов управления веб-сервера. События всплывают на сервере через запросы формы после возврата. Рассмотрим следующий пример кнопки Web Forms нажмите кнопку:

*Counter.ascx*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

В Blazor можно регистрировать обработчики событий DOM UI `@on{event}`напрямую с помощью директивных атрибутов формы. Заполнитель `{event}` представляет название события. Например, вы можете слушать кнопки кликов, как это:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

Обработчики событий могут принять дополнительный аргумент, конкретный для конкретных событий, чтобы предоставить более подробную информацию о событии. Например, события мыши `MouseEventArgs` могут быть аргументом, но это не требуется.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

Вместо того, чтобы ссылаться на группу метода для обработчика событий, можно использовать выражение лямбда. Выражение lambda позволяет закрыть по сравнению с другими значениями в области.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

Обработчики событий могут выполняться синхронно или синхронно. Например, обработчик событий выполняет `OnClick` асинхронно:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

После обработки события компонент отображается для учета любых изменений состояния компонента. С помощью асинхронных обработчиков событий компонент отображается сразу после завершения выполнения обработчика. Компонент визуалируется *снова* после `Task` асинхронного завершения. Этот асинхронный режим выполнения предоставляет возможность рендеринга некоторого `Task` соответствующего uI, пока асинхронный еще продолжается.

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

Компоненты могут также определять свои собственные события, определяя параметр компонента типа. `EventCallback<TValue>` Обратные вызовы событий поддерживают все вариации обработчиков событий DOM UI: дополнительные аргументы, синхронные или асинхронные, группы методов или выражения лямбды.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>привязка данных,

Blazor предоставляет простой механизм привязывания данных из компонента uI в состояние компонента. Этот подход отличается от функций в ASP.NET Web-форм для связывания данных от источников данных к элементам управления uI. Мы рассмотрим обработку данных из различных источников данных в разделе [Dealing with data.](data.md)

Чтобы создать двусторонню привязку данных от компонента uI `@bind` к состоянию компонента, используйте атрибут директивы. В следующем примере значение флажка привязано `isChecked` к полю.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

При визуализации компонент устанавливается значение флажка к значению `isChecked` поля. Когда пользователь переключает флажок, `onchange` событие сражается и `isChecked` поле настроено на новое значение. Синтаксис `@bind` в данном случае эквивалентен следующей разметке:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Чтобы изменить событие, используемое для `@bind:event` связывания, используйте атрибут.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

Компоненты также могут поддерживать привязку данных к их параметрам. Для связывания данных определите параметр обратного вызова события с тем же именем, что и параметр bindable. К названию добавляется суффикс "Измененный".

*PasswordBox.razor*

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

Чтобы сгваить привязку данных к базовому элементу uI, установите `@bind` значение и обгоните событие непосредственно на элементе uI вместо использования атрибута.

Чтобы привязаться к параметру компонента, используйте `@bind-{Parameter}` атрибут, чтобы указать параметр, к которому вы хотите привязать.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Изменения состояний

Если состояние компонента изменилось за пределами обычного события или обратного вызова события, то компонент должен вручную сигнализировать о необходимости повторного отображаемого. Чтобы сигнализировать об изменении состояния `StateHasChanged` компонента, позвоните в метод на компоненте.

В приведенном ниже примере компонент отображает `AppState` сообщение из службы, которое может быть обновлено другими частями приложения. Компонент регистрирует свой `StateHasChanged` метод `AppState.OnChange` с событием, чтобы компонент визуализировался всякий раз, когда сообщение обновляется.

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

## <a name="component-lifecycle"></a>Цикл жизни компонентов

В рамках ASP.NET Web Forms есть четко определенные методы жизненного цикла для модулей, страниц и элементов управления. Например, следующий элемент управления реализует `Init`обработчики событий для событий , `Load`и `UnLoad` жизненного цикла:

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Компоненты Blazor также имеют четко определенный жизненный цикл. Жизненный цикл компонента может быть использован для инициализации состояния компонентов и реализации передовых поведения компонентов.

Все методы жизненного цикла компонентов Blazor имеют как синхронные, так и асинхронные версии. Компонентная визуализация синхронна. Нельзя запускать асинхронную логику как часть рендеринга компонентов. Вся асинхронная логика `async` должна выполняться как часть метода жизненного цикла.

### <a name="oninitialized"></a>На Первоначальный

`OnInitialized` Методы `OnInitializedAsync` и методы используются для инициализации компонента. Компонент обычно инициализируется после его первой визуализации. После того, как компонент инициализирован, он может быть отрисован несколько раз, прежде чем он в конечном итоге удаляется. Метод `OnInitialized` аналогичен `Page_Load` событию в ASP.NET веб-форм страниц и элементов управления.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>На ПаразамносSet

`OnParametersSet` Методы `OnParametersSetAsync` и методы вызываются, когда компонент получил параметры от своего родителя и значение присваивается свойствам. Эти методы выполняются после инициализации компонента и *каждый раз, когда компонент визуализироваться.*

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

`OnAfterRender` Методы `OnAfterRenderAsync` и методы называются после завершения рендеринга компонента. На данный момент населяются ссылки элементов и компонентов (подробнее об этих понятиях ниже). Интерактивная активность с браузером включена в этой точке. Взаимодействие с выполнением DOM и JavaScript может безопасно.

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

`OnAfterRender`и `OnAfterRenderAsync` *не называются при предварительной рендеринге на сервере.*

Параметр `firstRender` `true` — это первый раз, когда компонент визуализироваться; в противном `false`случае, его значение .

### <a name="idisposable"></a>IDisposable

Компоненты Blazor `IDisposable` могут осуществляться для удаления ресурсов при удалении компонента из uI. Компонент Razor может `IDispose` реализовать `@implements` с помощью директивы:

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

## <a name="capture-component-references"></a>Ссылки на компонент захвата

В ASP.NET Web Forms обычно можно манипулировать экземпляром управления непосредственно в коде, ссылаясь на его идентификатор. В Blazor также можно запечатлеть и манипулировать ссылкой на компонент, хотя это гораздо реже.

Чтобы зафиксировать ссылку на `@ref` компоненты в Blazor, используйте атрибут директивы. Значение атрибута должно совпадать с именем поля settable с тем же типом, что и ссылки на компонент.

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

При визуализации родительского компонента поле заполняется экземпляром детского компонента. Затем можно вызвать методы на примере компонента или иным образом манипулировать иным образом.

Манипулирование состоянием компонента непосредственно с использованием ссылок компонентов не рекомендуется. Это предотвращает автоматический отрисованный компонент в нужное время.

## <a name="capture-element-references"></a>Ссылки элемента захвата

Компоненты Blazor могут фиксировать ссылки на элемент. В отличие от управления HTML-серверами в ASP.NET Web-форм, вы не можете манипулировать DOM напрямую, используя ссылку на элемент blazor. Blazor обрабатывает большинство взаимодействий DOM для вас, используя алгоритм диффинга DOM. Ссылки на захваченные элементы в Blazor непрозрачны. Тем не менее, они используются для передачи определенной ссылки элемента в вызове Interop JavaScript. Для получения дополнительной информации о JavaScript interop, [см. ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Шаблонные компоненты

В ASP.NET веб-формах можно создавать *шаблонные элементы управления.* Шаблонные элементы управления позволяют разработчику указать часть HTML, используемую для визуализации управления контейнером. Механика создания шаблонных элементов управления сервером сложна, но они позволяют мощным сценариям визуализации данных настраиваемым способом. Примеры шаблонных `Repeater` элементов управления включают и `DataList`.

Компоненты Blazor также можно шаблонировать путем `RenderFragment` `RenderFragment<T>`определения параметров компонентов типа или . A `RenderFragment` представляет собой кусок разметки Razor, который затем может быть отрисован компонентом. A `RenderFragment<T>` — это кусок разметки Razor, который принимает параметр, который может быть указан при визуализации фрагмента визы.

### <a name="child-content"></a>Детский контент

Компоненты Blazor могут отображать `RenderFragment` содержимое своего ребенка как содержимое и отображать его как часть рендеринга компонентов. Чтобы захватить содержимое ребенка, `RenderFragment` определите `ChildContent`параметр компонента типа и назовите его.

*ChildContentComponent.razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Родительский компонент может поставлять содержимое ребенка с помощью обычного синтаксиса Razor.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Параметры шаблона

Шаблонированный компонент Blazor может также определить `RenderFragment` несколько параметров компонента типа или. `RenderFragment<T>` Параметр для `RenderFragment<T>` можно указать при вызове. Чтобы указать общий параметр типа `@typeparam` для компонента, используйте директиву Razor.

*SimpleListView.razor*

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

При использовании шаблонного компонента параметры шаблона могут быть указаны с помощью элементов детского использования, которые соответствуют названиям параметров. Компонентные аргументы `RenderFragment<T>` типа, пройденные `context`как элементы, имеют неявный параметр под названием. Можно изменить имя параметра реализации `Context` с помощью атрибута на элементе ребенка. Любые параметры общего типа могут быть указаны с помощью атрибута, который соответствует названию параметра типа. Параметр типа будет выведен, если это возможно:

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

Выход этого компонента выглядит следующим образом:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>Файл с кодом программной части

Компонент Blazor обычно авторизуется в одном файле *.razor.* Тем не менее, можно также разделить код и разметку с помощью файла с кодом. Чтобы использовать файл компонента, добавьте файл C,s, который соответствует названию файла компонента, но с добавлением *расширения .cs* *(Counter.razor.cs).* Используйте файл C-класса для определения базового класса для компонента. Вы можете назвать базовый класс все, что вы хотите, но это общее имя класса `Base` так же, как компонент класса, но с расширением добавил (`CounterBase`). Класс, основанный на компонентах, также должен быть получен из `ComponentBase`. Затем, в файл компонента Razor, добавьте директиву, `@inherits` `@inherits CounterBase`чтобы указать базовый класс для компонента ().

*Counter.razor*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

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

Видимость членов компонента в базовом классе `protected` должна `public` быть или быть видимой для класса компонентов.

## <a name="additional-resources"></a>Дополнительные ресурсы

Предыдущее не является исчерпывающим обращением ко всем аспектам компонентов Blazor. Для получения дополнительной информации о том, как [создавать и использовать ASP.NET компоненты Core Razor,](/aspnet/core/blazor/components)см.

>[!div class="step-by-step"]
>[Предыдущий](app-startup.md)
>[Следующий](pages-routing-layouts.md)
