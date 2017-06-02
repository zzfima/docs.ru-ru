---
title: "Практическое руководство. Преобразование входящих утверждений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Практическое руководство. Преобразование входящих утверждений
## Применение  
  
-   Основой идентификатора Microsoft® Windows® \(WIF\)  
  
-   Веб\-формы ASP.NET®  
  
## Сводка  
 Это предоставляет подробные пошаговые процедуры по созданию простого утверждение\- осведомленное приложения веб\-форм ASP.NET и входящих утверждения.  Он также предоставляет инструкции для тестирования приложения проверить, что преобразованные утверждения, когда приложение выполнитьо.  
  
## Содержимое  
  
-   Назначения  
  
-   Общие сведения  
  
-   Сводка шагов  
  
-   Шаг 1. создание простого приложения веб\-форм ASP.NET  
  
-   Шаг 2 \- реализовать преобразование утверждений с помощью пользовательского ClaimsAuthenticationManager  
  
-   Шаг 3 \- теста решение  
  
## Назначения  
  
-   Настройка приложения веб\-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Преобразование входящих утверждений, добавление роли sysadmin утверждения  
  
-   Проверьте приложение веб\-формы ASP.NET увидеть, если он работает корректно  
  
## Общие сведения  
 WIF предоставляет класс с именем <xref:System.Security.Claims.ClaimsAuthenticationManager>, который позволяет пользователям изменять утверждения перед их к приложению проверяющей стороны \(проверяющая сторона использует версию\).  <xref:System.Security.Claims.ClaimsAuthenticationManager> полезно для отключения забот между проверкой подлинности и основным кодом приложения.  В приведенном ниже примере демонстрируется добавление роли для утверждений <xref:System.Security.Claims.ClaimsPrincipal>, во входящем может потребоваться категорией еще не присвоена.  
  
## Сводка шагов  
  
-   Шаг 1. создание простого приложения веб\-форм ASP.NET  
  
-   Шаг 2 \- реализовать преобразование утверждений с помощью пользовательского ClaimsAuthenticationManager  
  
-   Шаг 3 \- теста решение  
  
## Шаг 1. создание простого приложения веб\-форм ASP.NET  
 На этом шаге создается новое приложение веб\-формы ASP.NET.  
  
#### Создать простое приложение ASP.NET  
  
1.  Visual Studio запуска в режиме повышенном имени администратора.  
  
2.  В Visual Studio нажмите кнопку **Файл**, нажмите кнопку **Создать** и нажмите кнопку **Проект**.  
  
3.  В окне **Создать проект**, нажмите кнопку **приложение веб\-формы ASP.NET**.  
  
4.  В **Имя** введите `TestApp` и нажмите клавишу **ОК**.  
  
5.  Щелкните правой кнопкой мыши проект **TestApp** в **Обозреватель решений**, а затем выберите **идентификатор и доступ**.  
  
6.  Окно **идентификатор и доступ**.  В **Поставщики** выберите **Проверьте приложение с локальной службой маркеров безопасности разработки**, затем нажмите кнопку **Применить**.  
  
7.  В *файле Default.aspx* замените существующие разметки следующим кодом, а затем сохраните файл.  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
8.  Откройте файл с выделенным кодом *Default.aspx.cs.* Замените существующий код следующим кодом, а затем сохраните файл.  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
## Шаг 2 \- реализовать преобразование утверждений с помощью пользовательского ClaimsAuthenticationManager  
 На этом этапе переопределении стандартная функциональность в классе <xref:System.Security.Claims.ClaimsAuthenticationManager> чтобы добавить роль администратора к входящему субъекту.  
  
#### Реализация преобразования утверждений с помощью пользовательского ClaimsAuthenticationManager  
  
1.  В Visual Studio щелкнув правой кнопкой мыши на решение, нажмите **Добавить**, а затем нажмите кнопку **Создать проект**.  
  
2.  В окне **Добавить новый проект** выберите **Библиотека классов** из шаблонов **Visual C\#** перечислены введите `ClaimsTransformation`, а затем нажмите клавишу **ОК**.  Новый проект будет создать в папке решения.  
  
3.  Щелкните правой кнопкой мыши на **Ссылки** под проектом **ClaimsTransformation**, а затем нажмите кнопку **Добавить ссылку**.  
  
4.  В окне **Диспетчер ссылок** выберите **System.IdentityModel** и нажмите кнопку **ОК**.  
  
5.  Откройте **Class1.cs** или если он не существует, то для **ClaimsTransformation** щелкните правой кнопкой мыши **Добавить**, а затем щелкните **классифицируйте…**  
  
6.  Добавьте следующий код в файл кода с помощью директивы:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Добавьте следующий класс в файле кода и метод.  
  
    > [!WARNING]
    >  В следующем коде для демонстрационных целей только; убедитесь, что проверяется в предполагаемые разрешения в рабочем коде.  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  Сохраните файл и выполните построение проекта **ClaimsTransformation**.  
  
9. В проекте **TestApp** ASP.NET, щелкнув правой кнопкой мыши на ссылках и нажмите кнопку **Добавить ссылку**.  
  
10. В окне **Диспетчер ссылок** выберите **Решение** из левого меню выберите **ClaimsTransformation** от заполненных параметров, а затем нажмите кнопку **ОК**.  
  
11. В файл web.config adapter, перейдите к записи **\<system.identityModel\>**.  Внутри элементов **\<identityConfiguration\>** добавьте следующую линию и сохраните файл.  
  
    ```  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## Шаг 3 \- теста решение  
 На этом этапе тестируемого приложения веб\-форм ASP.NET и проверить, что утверждения, когда пользователь вход с проверкой подлинности с помощью форм.  
  
#### Тестирования приложения веб\-форм ASP.NET для утверждений с использованием проверки подлинности с помощью форм  
  
1.  Нажмите клавишу **F5** для построения и запуска приложения.  Необходимо с *Default.aspx.*  
  
2.  На *странице Default.aspx*, вы должны увидеть таблицу под заголовок **Собственные утверждения**, который включает **Поставщик**, **OriginalIssuer**, **Тип**, **Значение** и утверждения **ValueType** данные об учетной записи.  Последняя строка должна следующим образом:  
  
    ||||||  
    |-|-|-|-|-|  
    |ЛОКАЛЬНЫЕ АДМИНИСТРИРОВАНИЯ|ЛОКАЛЬНЫЕ АДМИНИСТРИРОВАНИЯ|http:\/\/schemas.microsoft.com\/ws\/2008\/06\/identity\/claims\/role|Admin|http:\/\/www.w3.org\/2001\/XMLSchema\#string|