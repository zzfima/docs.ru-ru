---
title: Страницы, маршрутизация и макеты
description: Узнайте, как создавать страницы в Блазор, работать с маршрутизацией на стороне клиента и управлять макетами страниц.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841237"
---
# <a name="pages-routing-and-layouts"></a>Страницы, маршрутизация и макеты

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET приложения Web Forms состоят из страниц, определенных в *ASPX* -файлах. Адрес каждой страницы зависит от его физического пути к файлу в проекте. Когда браузер выполняет запрос к странице, содержимое страницы динамически отображается на сервере. Учетные записи отрисовки как HTML-разметки страницы, так и ее серверных элементов управления.

В Блазор каждая страница в приложении является компонентом, обычно определяемым в файле с *расширением Razor* , с одним или несколькими указанными маршрутами. Маршрутизация в основном происходит на стороне клиента без участия конкретного запроса сервера. Сначала браузер выполняет запрос к корневому адресу приложения. После этого корневой компонент `Router` в приложении Блазор обрабатывает перехват запросов навигации и их в нужный компонент.

Блазор также поддерживает *глубокую компоновку*. Глубокое связывание происходит, когда браузер выполняет запрос к конкретному маршруту, отличному от корневого каталога приложения. Запросы на детализированные ссылки, отправленные на сервер, направляются в приложение Блазор, которое затем направляет клиентский запрос к нужному компоненту.

Простая страница в веб-формах ASP.NET может содержать следующую разметку:

*Имя. aspx*

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

Эквивалентная страница в приложении Блазор будет выглядеть следующим образом:

*Name. Razor*

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a>Создание страниц

Чтобы создать страницу в Блазор, создайте компонент и добавьте директиву `@page` Razor, чтобы указать маршрут для компонента. Директива `@page` принимает один параметр, который является шаблоном маршрута, добавляемым к этому компоненту.

```razor
@page "/counter"
```

Параметр шаблона Route является обязательным. В отличие от веб-форм ASP.NET, маршрут к компоненту Блазор *не* определяется местоположением файла (хотя это может быть компонент, добавляемый в будущем).

Синтаксис шаблона маршрута — это тот же базовый синтаксис, который используется для маршрутизации в веб-формах ASP.NET. Параметры маршрута указываются в шаблоне с помощью фигурных скобок. Блазор привязывает значения маршрута к параметрам компонента с тем же именем (без учета регистра).

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

Можно также указать ограничения на значение параметра Route. Например, чтобы ограничить идентификатор продукта `int`:

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

Полный список ограничений маршрута, поддерживаемых Блазор, см. в разделе [ограничения маршрута](/aspnet/core/blazor/routing#route-constraints).

## <a name="router-component"></a>Компонент маршрутизатора

Маршрутизация в Блазор обрабатывается компонентом `Router`. Компонент `Router` обычно используется в корневом компоненте приложения (*app. Razor*).

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

Компонент `Router` обнаруживает маршрутизируемые компоненты в указанном `AppAssembly` и в дополнительно заданном `AdditionalAssemblies`. Когда браузер переходит по, `Router` перехватывает навигацию и отображает содержимое его параметра `Found` с извлеченным `RouteData`, если маршрут соответствует адресу, в противном случае `Router` отображает его параметр `NotFound`.

Компонент `RouteView` обрабатывает сопоставленный компонент, заданный `RouteData`, с его макетом, если он имеется. Если сопоставляемый компонент не имеет макета, используется дополнительно заданный `DefaultLayout`.

Компонент `LayoutView` визуализирует свое дочернее содержимое в указанном макете. Далее в этой главе мы рассмотрим макеты более подробно.

## <a name="navigation"></a>Навигация

В ASP.NET Web Forms вы запускаете навигацию на другой странице, возвращая ответ перенаправления в браузер. Пример:

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

Возвращение ответа перенаправления обычно не поддерживается в Блазор. Блазор не использует модель "запрос-ответ". Однако вы можете активировать навигацию в браузере напрямую, как и в случае с JavaScript.

Блазор предоставляет службу `NavigationManager`, которую можно использовать для:

- Получить текущий адрес браузера
- Получить базовый адрес
- Переходы по триггерам
- Получать уведомления при изменении адреса

Для перехода к другому адресу используйте метод `NavigateTo`:

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

Описание всех членов `NavigationManager` см. в разделе [вспомогательные методы состояния URI и навигации](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).

## <a name="base-urls"></a>Базовые URL-адреса

Если приложение Блазор развертывается по базовому пути, необходимо указать базовый URL-адрес в метаданных страницы, используя тег `<base>` для свойства маршрутизации к работе. Если страница узла для приложения отображается на сервере с помощью Razor, то можно использовать синтаксис `~/`, чтобы указать базовый адрес приложения. Если страница узла является статическим HTML, необходимо явно указать базовый URL-адрес.

```html
<base href="~/" />
```

## <a name="page-layout"></a>Макет страницы

Макет страницы в веб-формах ASP.NET обрабатывается главными страницами. Главные страницы определяют шаблон с одним или несколькими заполнителями содержимого, которые затем могут быть предоставлены отдельными страницами. Главные страницы определяются в файлах *master* и начинаются с директивы `<%@ Master %>`. Содержимое *главных* файлов задается как страница *ASPX* , но с добавлением элементов управления `<asp:ContentPlaceHolder>`, помечающих страницы для передачи содержимого.

*Site. master*

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

В Блазор макет страницы обрабатывается с помощью компонентов макета. Компоненты макета наследуют от `LayoutComponentBase`, который определяет одно `Body` свойство типа `RenderFragment`, которое можно использовать для визуализации содержимого страницы.

*Маинлайаут. Razor*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

При отображении страницы с макетом Эта страница подготавливается к просмотру в пределах содержимого указанного макета в том месте, где макет отрисовывает свое свойство `Body`.

Чтобы применить макет к странице, используйте директиву `@layout`:

```razor
@layout MainLayout
```

Можно указать макет для всех компонентов в папке и вложенных папках, используя файл *_Imports. Razor* . Можно также указать макет по умолчанию для всех страниц с помощью [компонента маршрутизатора](#router-component).

Главные страницы могут определять несколько заполнителей содержимого, но макеты в Блазор имеют только одно свойство `Body`. Это ограничение компонентов макета Блазор будет рассмотрено в следующем выпуске.

Главные страницы в веб-формах ASP.NET могут быть вложенными. То есть Главная страница может также использовать главную страницу. Компоненты макета в Блазор могут быть вложенными. Компонент макета можно применить к компоненту макета. Содержимое внутреннего макета будет отображаться во внешнем макете.

*Чилдлайаут. Razor*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*Index. Razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

Отображаемые выходные данные для страницы будут выглядеть следующим образом:

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

Макеты в Блазор обычно не определяют корневые элементы HTML для страницы (`<html>`, `<body>`, `<head>`и т. д.). Корневые элементы HTML определяются на странице узла приложения Блазор, которая используется для отрисовки исходного HTML-содержимого приложения (см. раздел [начальная загрузка блазор](project-structure.md#bootstrap-blazor)). Страница узла может визуализировать несколько корневых компонентов для приложения с окружающей разметкой.

Компоненты в Блазор, включая страницы, не могут визуализировать `<script>` Теги. Это ограничение отрисовки существует, так как `<script>` Теги загружаются один раз, а затем не могут быть изменены. Если вы попытаетесь динамически визуализировать Теги с помощью синтаксис Razor, может произойти непредвиденное поведение. Вместо этого все теги `<script>` должны быть добавлены на страницу узла приложения.

>[!div class="step-by-step"]
>[Назад](components.md)
>[Вперед](state-management.md)
