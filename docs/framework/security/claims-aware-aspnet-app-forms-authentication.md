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
ms.locfileid: "33408623"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="35c74-102">Практическое руководство. Создание приложения ASP.NET, поддерживающего утверждения, использующего проверку подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="35c74-103">Применение</span><span class="sxs-lookup"><span data-stu-id="35c74-103">Applies To</span></span>  
  
-   <span data-ttu-id="35c74-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="35c74-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="35c74-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="35c74-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="35c74-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="35c74-106">Summary</span></span>  
 <span data-ttu-id="35c74-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений, использующего проверку подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="35c74-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="35c74-108">Оно также содержит инструкции по тестированию приложения для проверки на наличие утверждений при входе пользователя с применением проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="35c74-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="35c74-109">Описание</span><span class="sxs-lookup"><span data-stu-id="35c74-109">Contents</span></span>  
  
-   <span data-ttu-id="35c74-110">Цели</span><span class="sxs-lookup"><span data-stu-id="35c74-110">Objectives</span></span>  
  
-   <span data-ttu-id="35c74-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="35c74-111">Overview</span></span>  
  
-   <span data-ttu-id="35c74-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="35c74-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="35c74-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35c74-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="35c74-114">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="35c74-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="35c74-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="35c74-116">Цели</span><span class="sxs-lookup"><span data-stu-id="35c74-116">Objectives</span></span>  
  
-   <span data-ttu-id="35c74-117">Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
-   <span data-ttu-id="35c74-118">Тестирование приложения веб-форм ASP.NET на правильность работы</span><span class="sxs-lookup"><span data-stu-id="35c74-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="35c74-119">Обзор</span><span class="sxs-lookup"><span data-stu-id="35c74-119">Overview</span></span>  
 <span data-ttu-id="35c74-120">Платформа WIF и реализованный в ней механизм проверки подлинности на основе утверждений входят в состав .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="35c74-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="35c74-121">Ранее для использования утверждения пользователя ASP.NET требовалась установка платформы WIF с последующим приведением интерфейсов к объектам субъектов, таким как `Thread.CurrentPrincipal` или `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="35c74-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="35c74-122">Теперь утверждения обрабатываются такими объектами субъектов в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="35c74-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="35c74-123">Включение платформы WIF в состав .NET 4.5 позволило оптимизировать проверку подлинности на основе форм, поскольку для всех применяющих эту технологию пользователей автоматически выполняется привязка утверждений.</span><span class="sxs-lookup"><span data-stu-id="35c74-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="35c74-124">Эти утверждения можно сразу же использовать в приложении ASP.NET с проверкой подлинности на основе форм, как показано в этом практическом руководстве.</span><span class="sxs-lookup"><span data-stu-id="35c74-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="35c74-125">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="35c74-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="35c74-126">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35c74-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="35c74-127">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="35c74-128">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="35c74-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="35c74-129">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35c74-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="35c74-130">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="35c74-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="35c74-131">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35c74-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="35c74-132">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="35c74-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="35c74-133">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="35c74-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="35c74-134">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35c74-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="35c74-135">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
 <span data-ttu-id="35c74-136">На этом шаге в файл конфигурации *Web.config* добавляется запись конфигурации. Также в файл *Default.aspx* вносятся изменения, позволяющие отображать сведения об утверждениях для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="35c74-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="35c74-137">Настройка приложения ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-137">To configure ASP.NET application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="35c74-138">В файле *Default.aspx* замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="35c74-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
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
  
     <span data-ttu-id="35c74-139">На этом шаге на страницу *Default.aspx* добавляется элемент управления GridView, который будет заполнен утверждениями, полученными в результате проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="35c74-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>  
  
2.  <span data-ttu-id="35c74-140">Сохраните файл *Default.aspx*, а затем откройте его файл кода программной части с именем *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="35c74-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="35c74-141">Замените существующий код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="35c74-141">Replace the existing code with the following:</span></span>  
  
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
  
     <span data-ttu-id="35c74-142">Приведенный выше код отображает утверждения о прошедшем проверку пользователе, в том числе для пользователей, прошедших проверку подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="35c74-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="35c74-143">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="35c74-143">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="35c74-144">На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="35c74-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="35c74-145">Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="35c74-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="35c74-146">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="35c74-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="35c74-147">В верхней правой части страницы *Default.aspx* будут представлены ссылки **Регистрация** и **Вход**.</span><span class="sxs-lookup"><span data-stu-id="35c74-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="35c74-148">Щелкните ссылку **Регистрация**.</span><span class="sxs-lookup"><span data-stu-id="35c74-148">Click **Register**.</span></span>  
  
2.  <span data-ttu-id="35c74-149">На странице **Регистрация** создайте учетную запись пользователя и щелкните **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="35c74-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="35c74-150">После создания учетной записи с использованием проверки подлинности на основе форм вход будет выполнен автоматически.</span><span class="sxs-lookup"><span data-stu-id="35c74-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>  
  
3.  <span data-ttu-id="35c74-151">После перенаправления на домашнюю страницу вы увидите таблицу под заголовком **Ваши утверждения**, содержащую сведения утверждений **Issuer**, **OriginalIssuer**, **Type**, **Value** и **ValueType** о вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="35c74-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
