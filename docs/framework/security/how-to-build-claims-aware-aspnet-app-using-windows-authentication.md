---
title: 'Как выполнить: Создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации Windows'
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 039fccde55dd48571e38f064f68b16480b65cb44
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650411"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="43e7f-102">Как выполнить: Создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="43e7f-103">Применение</span><span class="sxs-lookup"><span data-stu-id="43e7f-103">Applies To</span></span>  
  
- <span data-ttu-id="43e7f-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="43e7f-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="43e7f-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="43e7f-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="43e7f-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="43e7f-106">Summary</span></span>  
 <span data-ttu-id="43e7f-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений, использующего проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="43e7f-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="43e7f-108">Оно также содержит инструкции по тестированию приложения для проверки на наличие утверждений при входе пользователя с применением проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="43e7f-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="43e7f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="43e7f-109">Contents</span></span>  
  
- <span data-ttu-id="43e7f-110">Цели</span><span class="sxs-lookup"><span data-stu-id="43e7f-110">Objectives</span></span>  
  
- <span data-ttu-id="43e7f-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="43e7f-111">Overview</span></span>  
  
- <span data-ttu-id="43e7f-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="43e7f-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="43e7f-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43e7f-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="43e7f-114">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
- <span data-ttu-id="43e7f-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="43e7f-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="43e7f-116">Цели</span><span class="sxs-lookup"><span data-stu-id="43e7f-116">Objectives</span></span>  
  
- <span data-ttu-id="43e7f-117">Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
- <span data-ttu-id="43e7f-118">Тестирование приложения веб-форм ASP.NET на правильность работы</span><span class="sxs-lookup"><span data-stu-id="43e7f-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="43e7f-119">Обзор</span><span class="sxs-lookup"><span data-stu-id="43e7f-119">Overview</span></span>  
 <span data-ttu-id="43e7f-120">Платформа WIF и реализованный в ней механизм проверки подлинности на основе утверждений входят в состав .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="43e7f-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="43e7f-121">Ранее для использования утверждения пользователя ASP.NET требовалась установка платформы WIF с последующим приведением интерфейсов к объектам субъектов, таким как `Thread.CurrentPrincipal` или `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="43e7f-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="43e7f-122">Теперь утверждения обрабатываются такими объектами субъектов в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="43e7f-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="43e7f-123">Включение платформы WIF в состав .NET 4.5 позволило оптимизировать проверку подлинности Windows, поскольку для всех применяющих учетные данные Windows пользователей автоматически выполняется привязка утверждений.</span><span class="sxs-lookup"><span data-stu-id="43e7f-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="43e7f-124">Эти утверждения можно сразу же использовать в приложении ASP.NET с проверкой подлинности Windows, как показано в этом практическом руководстве.</span><span class="sxs-lookup"><span data-stu-id="43e7f-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="43e7f-125">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="43e7f-125">Summary of Steps</span></span>  
  
- <span data-ttu-id="43e7f-126">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43e7f-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="43e7f-127">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
- <span data-ttu-id="43e7f-128">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="43e7f-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="43e7f-129">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43e7f-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="43e7f-130">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43e7f-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="43e7f-131">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43e7f-131">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="43e7f-132">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="43e7f-133">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="43e7f-134">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="43e7f-135">После создания проекта **TestApp** щелкните его в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="43e7f-136">Свойства проекта будут отображаться в панели **Свойства** ниже **обозревателя решений**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="43e7f-137">Присвойте свойству **Проверка подлинности Windows** значение **Включено**.</span><span class="sxs-lookup"><span data-stu-id="43e7f-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="43e7f-138">Проверка подлинности Windows в новых приложениях ASP.NET по умолчанию отключена, поэтому ее необходимо включать вручную.</span><span class="sxs-lookup"><span data-stu-id="43e7f-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="43e7f-139">Шаг 2. Настройка приложения веб-форм ASP.NET на применение утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="43e7f-140">На этом шаге в файл конфигурации *Web.config* добавляется запись конфигурации. Также в файл *Default.aspx* вносятся изменения, позволяющие отображать сведения об утверждениях для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="43e7f-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="43e7f-141">Настройка приложения ASP.NET на применение утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1. <span data-ttu-id="43e7f-142">В проекте **TestApp** в файле *Default.aspx* замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="43e7f-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
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
  
     <span data-ttu-id="43e7f-143">На этом шаге на страницу *Default.aspx* добавляется элемент управления GridView, который будет заполнен утверждениями, полученными в результате проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="43e7f-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2. <span data-ttu-id="43e7f-144">Сохраните файл *Default.aspx*, а затем откройте его файл кода программной части с именем *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="43e7f-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="43e7f-145">Замените существующий код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="43e7f-145">Replace the existing code with the following:</span></span>  
  
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
  
     <span data-ttu-id="43e7f-146">Приведенный выше код демонстрирует утверждения о прошедшем проверку пользователе.</span><span class="sxs-lookup"><span data-stu-id="43e7f-146">The above code will display claims about an authenticated user.</span></span>  
  
3. <span data-ttu-id="43e7f-147">Чтобы изменить тип проверки подлинности приложения, измените блок **\<authentication>** в разделе **\<system.web>** корневого файла *Web.config* проекта таким образом, чтобы в нем содержалась только следующая запись конфигурации:</span><span class="sxs-lookup"><span data-stu-id="43e7f-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4. <span data-ttu-id="43e7f-148">Наконец, измените блок **\<authorization>** в разделе **\<system.web>** того же файла *Web.config*, чтобы реализовать принудительную проверку подлинности:</span><span class="sxs-lookup"><span data-stu-id="43e7f-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="43e7f-149">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="43e7f-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="43e7f-150">На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="43e7f-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="43e7f-151">Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="43e7f-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1. <span data-ttu-id="43e7f-152">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="43e7f-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="43e7f-153">В верхней правой части страницы появятся страница *Default.aspx*, а также имя учетной записи (с доменным именем) в качестве прошедшего проверку пользователя.</span><span class="sxs-lookup"><span data-stu-id="43e7f-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="43e7f-154">Кроме того, на странице должна быть представлена таблица с утверждениями, полученными от учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="43e7f-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>
