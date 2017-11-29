---
title: "Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, использующего проверку подлинности Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 676a03678cbdf6fe08e628806df2a1853fb71718
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a>Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, использующего проверку подлинности Windows
## <a name="applies-to"></a>Применение  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Веб-формы ASP.NET®  
  
## <a name="summary"></a>Сводка  
 В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений, использующего проверку подлинности Windows. Оно также содержит инструкции по тестированию приложения для проверки на наличие утверждений при входе пользователя с применением проверки подлинности Windows.  
  
## <a name="contents"></a>Описание  
  
-   Цели  
  
-   Обзор  
  
-   Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows  
  
-   Шаг 3. Тестирование решения  
  
## <a name="objectives"></a>Цели  
  
-   Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows  
  
-   Тестирование приложения веб-форм ASP.NET на правильность работы  
  
## <a name="overview"></a>Обзор  
 Платформа WIF и реализованный в ней механизм проверки подлинности на основе утверждений входят в состав .NET 4.5. Ранее для использования утверждения пользователя ASP.NET требовалась установка платформы WIF с последующим приведением интерфейсов к объектам субъектов, таким как `Thread.CurrentPrincipal` или `HttpContext.Current.User`. Теперь утверждения обрабатываются такими объектами субъектов в автоматическом режиме.  
  
 Включение платформы WIF в состав .NET 4.5 позволило оптимизировать проверку подлинности Windows, поскольку для всех применяющих учетные данные Windows пользователей автоматически выполняется привязка утверждений. Эти утверждения можно сразу же использовать в приложении ASP.NET с проверкой подлинности Windows, как показано в этом практическом руководстве.  
  
## <a name="summary-of-steps"></a>Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows  
  
-   Шаг 3. Тестирование решения  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Шаг 1. Создание простого приложения веб-форм ASP.NET  
 На этом шаге создается новое приложение веб-форм ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Создание простого приложения ASP.NET  
  
1.  Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.  
  
2.  В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.  
  
3.  В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.  
  
4.  После создания проекта **TestApp** щелкните его в **обозревателе решений**. Свойства проекта будут отображаться в панели **Свойства** ниже **обозревателя решений**. Присвойте свойству **Проверка подлинности Windows** значение **Включено**.  
  
    > [!WARNING]
    >  Проверка подлинности Windows в новых приложениях ASP.NET по умолчанию отключена, поэтому ее необходимо включать вручную.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows  
 На этом шаге в файл конфигурации *Web.config* добавляется запись конфигурации. Также в файл *Default.aspx* вносятся изменения, позволяющие отображать сведения об утверждениях для учетной записи.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a>Настройка приложения ASP.NET на применение утверждений с использованием проверки подлинности Windows  
  
1.  В проекте **TestApp** в файле *Default.aspx* замените существующую разметку следующей:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
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
  
     На этом шаге на страницу *Default.aspx* добавляется элемент управления GridView, который будет заполнен утверждениями, полученными в результате проверки подлинности Windows.  
  
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
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     Приведенный выше код демонстрирует утверждения о прошедшем проверку пользователе.  
  
3.  Чтобы изменить тип проверки подлинности приложения, измените блок **\<authentication>** в разделе **\<system.web>** корневого файла *Web.config* проекта таким образом, чтобы в нем содержалась только следующая запись конфигурации:  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  Наконец, измените блок **\<authorization>** в разделе **\<system.web>** того же файла *Web.config*, чтобы реализовать принудительную проверку подлинности:  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a>Шаг 3. Тестирование решения  
 На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности Windows.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности Windows  
  
1.  Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его. В верхней правой части страницы появятся страница *Default.aspx*, а также имя учетной записи (с доменным именем) в качестве прошедшего проверку пользователя. Кроме того, на странице должна быть представлена таблица с утверждениями, полученными от учетной записи Windows.
