---
title: Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, использующего проверку подлинности на основе форм
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 851a856d291da78265e9eac73e9e06028e24ef2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a>Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, использующего проверку подлинности на основе форм
## <a name="applies-to"></a>Применение  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Веб-формы ASP.NET®  
  
## <a name="summary"></a>Сводка  
 В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений, использующего проверку подлинности на основе форм. Оно также содержит инструкции по тестированию приложения для проверки на наличие утверждений при входе пользователя с применением проверки подлинности на основе форм.  
  
## <a name="contents"></a>Описание  
  
-   Цели  
  
-   Обзор  
  
-   Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм  
  
-   Шаг 3. Тестирование решения  
  
## <a name="objectives"></a>Цели  
  
-   Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм  
  
-   Тестирование приложения веб-форм ASP.NET на правильность работы  
  
## <a name="overview"></a>Обзор  
 Платформа WIF и реализованный в ней механизм проверки подлинности на основе утверждений входят в состав .NET 4.5. Ранее для использования утверждения пользователя ASP.NET требовалась установка платформы WIF с последующим приведением интерфейсов к объектам субъектов, таким как `Thread.CurrentPrincipal` или `HttpContext.Current.User`. Теперь утверждения обрабатываются такими объектами субъектов в автоматическом режиме.  
  
 Включение платформы WIF в состав .NET 4.5 позволило оптимизировать проверку подлинности на основе форм, поскольку для всех применяющих эту технологию пользователей автоматически выполняется привязка утверждений. Эти утверждения можно сразу же использовать в приложении ASP.NET с проверкой подлинности на основе форм, как показано в этом практическом руководстве.  
  
## <a name="summary-of-steps"></a>Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм  
  
-   Шаг 3. Тестирование решения  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Шаг 1. Создание простого приложения веб-форм ASP.NET  
 На этом шаге создается новое приложение веб-форм ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Создание простого приложения ASP.NET  
  
1.  Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.  
  
2.  В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.  
  
3.  В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм  
 На этом шаге в файл конфигурации *Web.config* добавляется запись конфигурации. Также в файл *Default.aspx* вносятся изменения, позволяющие отображать сведения об утверждениях для учетной записи.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a>Настройка приложения ASP.NET на применение утверждений с использованием проверки подлинности на основе форм  
  
1.  В файле *Default.aspx* замените существующую разметку следующей:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
     На этом шаге на страницу *Default.aspx* добавляется элемент управления GridView, который будет заполнен утверждениями, полученными в результате проверки подлинности на основе форм.  
  
2.  Сохраните файл *Default.aspx*, а затем откройте его файл кода программной части с именем *Default.aspx.cs*. Замените существующий код следующим кодом:  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     Приведенный выше код отображает утверждения о прошедшем проверку пользователе, в том числе для пользователей, прошедших проверку подлинности на основе форм.  
  
## <a name="step-3--test-your-solution"></a>Шаг 3. Тестирование решения  
 На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности на основе форм.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности на основе форм  
  
1.  Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его. В верхней правой части страницы *Default.aspx* будут представлены ссылки **Регистрация** и **Вход**. Щелкните ссылку **Регистрация**.  
  
2.  На странице **Регистрация** создайте учетную запись пользователя и щелкните **Зарегистрироваться**. После создания учетной записи с использованием проверки подлинности на основе форм вход будет выполнен автоматически.  
  
3.  После перенаправления на домашнюю страницу вы увидите таблицу под заголовком **Ваши утверждения**, содержащую сведения утверждений **Issuer**, **OriginalIssuer**, **Type**, **Value** и **ValueType** о вашей учетной записи.
