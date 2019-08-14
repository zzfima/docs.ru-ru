---
title: Как создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации на основе форм
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: 75db96a621d7863ef445efb24814111b34da6960
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971838"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="eadba-102">Как создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>

## <a name="applies-to"></a><span data-ttu-id="eadba-103">Применение</span><span class="sxs-lookup"><span data-stu-id="eadba-103">Applies To</span></span>

- <span data-ttu-id="eadba-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="eadba-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>

- <span data-ttu-id="eadba-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="eadba-105">ASP.NET® Web Forms</span></span>

## <a name="summary"></a><span data-ttu-id="eadba-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="eadba-106">Summary</span></span>

<span data-ttu-id="eadba-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений, использующего проверку подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="eadba-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="eadba-108">Оно также содержит инструкции по тестированию приложения для проверки на наличие утверждений при входе пользователя с применением проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="eadba-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>

## <a name="contents"></a><span data-ttu-id="eadba-109">Описание</span><span class="sxs-lookup"><span data-stu-id="eadba-109">Contents</span></span>

- <span data-ttu-id="eadba-110">Цели</span><span class="sxs-lookup"><span data-stu-id="eadba-110">Objectives</span></span>

- <span data-ttu-id="eadba-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="eadba-111">Overview</span></span>

- <span data-ttu-id="eadba-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="eadba-112">Summary of Steps</span></span>

- <span data-ttu-id="eadba-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eadba-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="eadba-114">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="eadba-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="eadba-115">Step 3 – Test Your Solution</span></span>

## <a name="objectives"></a><span data-ttu-id="eadba-116">Цели</span><span class="sxs-lookup"><span data-stu-id="eadba-116">Objectives</span></span>

- <span data-ttu-id="eadba-117">Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>

- <span data-ttu-id="eadba-118">Тестирование приложения веб-форм ASP.NET на правильность работы</span><span class="sxs-lookup"><span data-stu-id="eadba-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>

## <a name="overview"></a><span data-ttu-id="eadba-119">Обзор</span><span class="sxs-lookup"><span data-stu-id="eadba-119">Overview</span></span>

<span data-ttu-id="eadba-120">Платформа WIF и реализованный в ней механизм проверки подлинности на основе утверждений входят в состав .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="eadba-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="eadba-121">Ранее для использования утверждения пользователя ASP.NET требовалась установка платформы WIF с последующим приведением интерфейсов к объектам субъектов, таким как `Thread.CurrentPrincipal` или `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="eadba-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="eadba-122">Теперь утверждения обрабатываются такими объектами субъектов в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="eadba-122">Now, claims are served automatically by these Principal objects.</span></span>

<span data-ttu-id="eadba-123">Включение платформы WIF в состав .NET 4.5 позволило оптимизировать проверку подлинности на основе форм, поскольку для всех применяющих эту технологию пользователей автоматически выполняется привязка утверждений.</span><span class="sxs-lookup"><span data-stu-id="eadba-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="eadba-124">Эти утверждения можно сразу же использовать в приложении ASP.NET с проверкой подлинности на основе форм, как показано в этом практическом руководстве.</span><span class="sxs-lookup"><span data-stu-id="eadba-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>

## <a name="summary-of-steps"></a><span data-ttu-id="eadba-125">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="eadba-125">Summary of Steps</span></span>

- <span data-ttu-id="eadba-126">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eadba-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="eadba-127">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="eadba-128">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="eadba-128">Step 3 – Test Your Solution</span></span>

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="eadba-129">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eadba-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

<span data-ttu-id="eadba-130">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eadba-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>

### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="eadba-131">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eadba-131">To create a simple ASP.NET application</span></span>

1. <span data-ttu-id="eadba-132">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="eadba-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>

2. <span data-ttu-id="eadba-133">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="eadba-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>

3. <span data-ttu-id="eadba-134">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eadba-134">In **Name**, enter `TestApp` and press **OK**.</span></span>

## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="eadba-135">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

<span data-ttu-id="eadba-136">На этом шаге в файл конфигурации *Web.config* добавляется запись конфигурации. Также в файл *Default.aspx* вносятся изменения, позволяющие отображать сведения об утверждениях для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="eadba-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>

### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="eadba-137">Настройка приложения ASP.NET на применение утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-137">To configure ASP.NET application for claims using Forms authentication</span></span>

1. <span data-ttu-id="eadba-138">В файле *Default.aspx* замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="eadba-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>

    ```aspx
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

    <span data-ttu-id="eadba-139">На этом шаге на страницу *Default.aspx* добавляется элемент управления GridView, который будет заполнен утверждениями, полученными в результате проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="eadba-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>

2. <span data-ttu-id="eadba-140">Сохраните файл *Default.aspx*, а затем откройте его файл кода программной части с именем *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="eadba-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="eadba-141">Замените существующий код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="eadba-141">Replace the existing code with the following:</span></span>

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

    <span data-ttu-id="eadba-142">Приведенный выше код отображает утверждения о прошедшем проверку пользователе, в том числе для пользователей, прошедших проверку подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="eadba-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>

## <a name="step-3--test-your-solution"></a><span data-ttu-id="eadba-143">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="eadba-143">Step 3 – Test Your Solution</span></span>

<span data-ttu-id="eadba-144">На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="eadba-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>

### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="eadba-145">Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="eadba-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>

1. <span data-ttu-id="eadba-146">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="eadba-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="eadba-147">В верхней правой части страницы *Default.aspx* будут представлены ссылки **Регистрация** и **Вход**.</span><span class="sxs-lookup"><span data-stu-id="eadba-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="eadba-148">Щелкните ссылку **Регистрация**.</span><span class="sxs-lookup"><span data-stu-id="eadba-148">Click **Register**.</span></span>

2. <span data-ttu-id="eadba-149">На странице **Регистрация** создайте учетную запись пользователя и щелкните **Зарегистрироваться**.</span><span class="sxs-lookup"><span data-stu-id="eadba-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="eadba-150">После создания учетной записи с использованием проверки подлинности на основе форм вход будет выполнен автоматически.</span><span class="sxs-lookup"><span data-stu-id="eadba-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>

3. <span data-ttu-id="eadba-151">После перенаправления на домашнюю страницу вы увидите таблицу под заголовком **Ваши утверждения**, содержащую сведения утверждений **Issuer**, **OriginalIssuer**, **Type**, **Value** и **ValueType** о вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="eadba-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
