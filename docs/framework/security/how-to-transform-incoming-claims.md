---
title: Практическое руководство. Преобразование входящих утверждений
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: 8673b4520d9727ae1aa78ef0bc9f435defb02598
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032339"
---
# <a name="how-to-transform-incoming-claims"></a>Практическое руководство. Преобразование входящих утверждений
## <a name="applies-to"></a>Применение  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Веб-формы ASP.NET®  
  
## <a name="summary"></a>Сводка  
 В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET, поддерживающего утверждения, и преобразованию входящих утверждений. Оно также содержит инструкции по тестированию приложения для проверки на наличие преобразованных утверждений во время выполнения приложения.  
  
## <a name="contents"></a>Описание  
  
-   Цели  
  
-   Обзор  
  
-   Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager  
  
-   Шаг 3. Тестирование решения  
  
## <a name="objectives"></a>Цели  
  
-   Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Преобразование входящих утверждений путем добавления утверждения роли администратора  
  
-   Тестирование приложения веб-форм ASP.NET на правильность работы  
  
## <a name="overview"></a>Обзор  
 WIF предоставляет класс с именем <xref:System.Security.Claims.ClaimsAuthenticationManager>, позволяющий пользователям изменять утверждения перед их представлением приложению проверяющей стороны (RP). <xref:System.Security.Claims.ClaimsAuthenticationManager> полезен для разделения проблем между проверкой подлинности и базовым кодом приложения. В приведенном ниже примере показано, как добавить роль в утверждения во входящем классе <xref:System.Security.Claims.ClaimsPrincipal>, который может потребоваться проверяющей стороне.  
  
## <a name="summary-of-steps"></a>Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager  
  
-   Шаг 3. Тестирование решения  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Шаг 1. Создание простого приложения веб-форм ASP.NET  
 На этом шаге создается новое приложение веб-форм ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Создание простого приложения ASP.NET  
  
1.  Запустите Visual Studio от имени администратора.  
  
2.  В Visual Studio в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
3.  В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.  
  
4.  В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.  
  
5.  В **обозревателе решений** щелкните правой кнопкой мыши проект **TestApp**, а затем выберите **Идентификация и доступ**.  
  
6.  Откроется окно **Идентификация и доступ**. В поле **Поставщики** выберите **Протестировать приложение с помощью локальной службы Development STS** и нажмите кнопку **Применить**.  
  
7.  В файле *Default.aspx* замените существующую разметку приведенной ниже, а затем сохраните файл.  
  
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
  
8.  Откройте файл кода программной части с именем *Default.aspx.cs*. Замените существующий код приведенным ниже, а затем сохраните файл.  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager  
 На этом шаге переопределяются функциональные возможности по умолчанию в классе <xref:System.Security.Claims.ClaimsAuthenticationManager> для добавления роли администратора во входящий субъект.  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager  
  
1.  В Visual Studio щелкните решение правой кнопкой мыши, выберите команду **Добавить** и пункт **Новый проект**.  
  
2.  В окне **Добавление нового проекта** выберите **Библиотека классов** в списке шаблонов **Visual C#**, введите `ClaimsTransformation` и затем нажмите кнопку **ОК**. В папке решения будет создан новый проект.  
  
3.  Щелкните правой кнопкой мыши элемент **Ссылки** в проекте **ClaimsTransformation** и выберите **Добавить ссылку**.  
  
4.  В окне **Диспетчер ссылок** выберите **System.IdentityModel**, а затем нажмите кнопку **ОК**.  
  
5.  Откройте **Class1.cs**, или если он не существует, щелкните правой кнопкой мыши **ClaimsTransformation**, выберите **Добавить** и щелкните **Класс...**  
  
6.  В файл кода добавьте следующие директивы using:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  В файл кода добавьте следующий класс и метод.  
  
    > [!WARNING]
    >  Следующий код приведен исключительно для демонстрации. Проверьте нужные разрешения в рабочем коде.  
  
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
  
8.  Сохраните файл и выполните сборку проекта **ClaimsTransformation**.  
  
9. В проекте ASP.NET **TestApp** щелкните правой кнопкой мыши "Ссылки", а затем выберите команду **Добавить ссылку**.  
  
10. В окне **Диспетчер ссылок** в левом меню выберите **Решения**, в заполненных параметрах выберите **ClaimsTransformation**, а затем нажмите кнопку **ОК**.  
  
11. В корневом файле **Web.config** перейдите к записи **\<system.identityModel>**. В элементах **\<identityConfiguration>** добавьте следующую строку и сохраните файл:  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a>Шаг 3. Тестирование решения  
 На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности на основе форм.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности на основе форм  
  
1.  Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его. Откроется страница *Default.aspx*.  
  
2.  На странице *Default.aspx* вы увидите таблицу под заголовком **Ваши утверждения**, содержащую сведения утверждений **Issuer**, **OriginalIssuer**, **Type**, **Value** и **ValueType** о вашей учетной записи. Последняя строка должна иметь следующий вид:  
  
    ||||||  
    |-|-|-|-|-|  
    |LOCAL AUTHORITY|LOCAL AUTHORITY|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|Администратор|http://www.w3.org/2001/XMLSchema#string|
