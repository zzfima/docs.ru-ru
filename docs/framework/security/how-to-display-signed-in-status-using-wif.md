---
title: "Практическое руководство. Отображение состояния входа с помощью WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 494e67b39187a2a38f29f994e17051430d90f708
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-signed-in-status-using-wif"></a><span data-ttu-id="b93c7-102">Практическое руководство. Отображение состояния входа с помощью WIF</span><span class="sxs-lookup"><span data-stu-id="b93c7-102">How To: Display Signed In Status Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="b93c7-103">Применение</span><span class="sxs-lookup"><span data-stu-id="b93c7-103">Applies To</span></span>  
  
-   <span data-ttu-id="b93c7-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span><span class="sxs-lookup"><span data-stu-id="b93c7-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span></span>  
  
-   <span data-ttu-id="b93c7-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="b93c7-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="b93c7-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="b93c7-106">Summary</span></span>  
 <span data-ttu-id="b93c7-107">В этом разделе описывается отображение состояния входа в приложении ASP.NET с поддержкой WIF.</span><span class="sxs-lookup"><span data-stu-id="b93c7-107">This topic describes how to display the sign in status in a WIF-enabled ASP.NET application.</span></span> <span data-ttu-id="b93c7-108">Платформа WIF предоставляет механизм для создания приложений с поддержкой утверждений, управления проверкой подлинности и авторизации ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="b93c7-108">WIF provides the mechanism for making your application claims-aware, and managing authentication and authorization for application resources.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="b93c7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b93c7-109">Contents</span></span>  
  
-   <span data-ttu-id="b93c7-110">Обзор</span><span class="sxs-lookup"><span data-stu-id="b93c7-110">Overview</span></span>  
  
-   <span data-ttu-id="b93c7-111">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="b93c7-111">Summary of Steps</span></span>  
  
-   <span data-ttu-id="b93c7-112">Шаг 1. Установка расширения для управления удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="b93c7-112">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="b93c7-113">Шаг 2. Создание приложения ASP.NET проверяющей стороны</span><span class="sxs-lookup"><span data-stu-id="b93c7-113">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="b93c7-114">Шаг 3. Включение локальной службы маркеров безопасности разработки для проверки подлинности пользователей</span><span class="sxs-lookup"><span data-stu-id="b93c7-114">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="b93c7-115">Шаг 4. Изменение приложения ASP.NET для отображения сведений о состоянии входа</span><span class="sxs-lookup"><span data-stu-id="b93c7-115">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="b93c7-116">Шаг 5. Проверка интеграции между платформой WIF и приложением ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-116">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="overview"></a><span data-ttu-id="b93c7-117">Обзор</span><span class="sxs-lookup"><span data-stu-id="b93c7-117">Overview</span></span>  
 <span data-ttu-id="b93c7-118">В этом разделе показано, как создать простое приложение на основе утверждений с помощью платформы WIF и реализовать отображение состояния входа для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b93c7-118">This topic demonstrates how to create a simple claims-aware application using WIF and how to easily display whether a user is signed in or not.</span></span> <span data-ttu-id="b93c7-119">При выполнении этих шагов используется локальная служба маркеров безопасности разработки, которая входит в состав расширения для управления удостоверениями и доступом Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b93c7-119">The following steps use the Local Development STS that is included with the Identity and Access Visual Studio Extension.</span></span> <span data-ttu-id="b93c7-120">Локальная служба маркеров безопасности разработки предназначена для тестирования и разработки среды, которая обеспечивает простую интеграцию утверждений в приложение.</span><span class="sxs-lookup"><span data-stu-id="b93c7-120">The Local Development STS is intended for a testing and development environment to provide a simple method of integrating claims into your application.</span></span> <span data-ttu-id="b93c7-121">Она не выполняет фактическую проверку подлинности и не запрашивает учетные данные, в связи с чем ее нельзя использовать в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="b93c7-121">It should never be used in a production environment, as it does not perform real authentication and credentials are not required.</span></span> <span data-ttu-id="b93c7-122">Тем не менее императивный код, используемый при выполнении этих действий, аналогичен тому, который будет применяться в готовом к работе приложении, использующем фактическую проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b93c7-122">However, the imperative code in the following steps is the same for a production-ready application using real authentication.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="b93c7-123">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="b93c7-123">Summary of Steps</span></span>  
  
-   <span data-ttu-id="b93c7-124">Шаг 1. Установка расширения для управления удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="b93c7-124">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="b93c7-125">Шаг 2. Создание приложения ASP.NET проверяющей стороны</span><span class="sxs-lookup"><span data-stu-id="b93c7-125">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="b93c7-126">Шаг 3. Включение локальной службы маркеров безопасности разработки для проверки подлинности пользователей</span><span class="sxs-lookup"><span data-stu-id="b93c7-126">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="b93c7-127">Шаг 4. Изменение приложения ASP.NET для отображения сведений о состоянии входа</span><span class="sxs-lookup"><span data-stu-id="b93c7-127">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="b93c7-128">Шаг 5. Проверка интеграции между платформой WIF и приложением ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-128">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="step-1--install-the-identity-and-access-extension"></a><span data-ttu-id="b93c7-129">Шаг 1. Установка расширения для управления удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="b93c7-129">Step 1 – Install the Identity and Access Extension</span></span>  
 <span data-ttu-id="b93c7-130">В этом разделе описывается настройка расширения для управления доступом и удостоверениями Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b93c7-130">This step describes how to configure the Identity and Access extension to Visual Studio 2012.</span></span> <span data-ttu-id="b93c7-131">Это расширение автоматизирует процесс настройки приложения для взаимодействия с конечными точками службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="b93c7-131">This extension automates the process of configuring your application to communicate with STS endpoints.</span></span>  
  
#### <a name="to-install-the-identity-and-access-extension"></a><span data-ttu-id="b93c7-132">Установка расширения для управления удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="b93c7-132">To install the Identity and Access extension</span></span>  
  
1.  <span data-ttu-id="b93c7-133">Запустите Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="b93c7-133">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="b93c7-134">В Visual Studio откройте меню **Сервис** и выберите пункт **Диспетчер расширений**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-134">In Visual Studio, click **Tools** and click **Extension Manager**.</span></span> <span data-ttu-id="b93c7-135">Появится окно **Диспетчер расширений**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-135">The **Extension Manager** window appears.</span></span>  
  
3.  <span data-ttu-id="b93c7-136">В окне **Диспетчер расширений** выберите **Сетевые расширения** в меню слева, а затем щелкните элемент **Коллекция Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-136">In **Extension Manager**, click **Online Extensions** from the left menu, then select **Visual Studio Gallery**.</span></span>  
  
4.  <span data-ttu-id="b93c7-137">В верхнем правом углу окна **Диспетчер расширений** выполните поиск строки *Удостоверения и доступ*.</span><span class="sxs-lookup"><span data-stu-id="b93c7-137">In the top right corner of **Extension Manager**, search for *Identity and Access*.</span></span>  
  
5.  <span data-ttu-id="b93c7-138">В результатах поиска появится элемент **Удостоверения и доступ**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-138">The **Identity and Access** item will appear in the search results.</span></span> <span data-ttu-id="b93c7-139">Щелкните его и нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-139">Click it, and then click **Download**.</span></span>  
  
6.  <span data-ttu-id="b93c7-140">Появится диалоговое окно **Скачать и установить**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-140">The **Download and Install** dialog appears.</span></span> <span data-ttu-id="b93c7-141">Если вы согласны с условиями лицензии, нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-141">If you agree with the license terms, click **Install**.</span></span>  
  
7.  <span data-ttu-id="b93c7-142">После окончания установки расширения **Удостоверения и доступ** перезапустите Visual Studio с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="b93c7-142">When the **Identity and Access** extension has finished installing, restart Visual Studio in administrator mode.</span></span>  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a><span data-ttu-id="b93c7-143">Шаг 2. Создание приложения ASP.NET проверяющей стороны</span><span class="sxs-lookup"><span data-stu-id="b93c7-143">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
 <span data-ttu-id="b93c7-144">В этом разделе описывается создание приложения проверяющей стороны на основе веб-форм ASP.NET, которое будет интегрировано с платформой WIF.</span><span class="sxs-lookup"><span data-stu-id="b93c7-144">This step describes how to create a relying party ASP.NET Web Forms application that will integrate with WIF.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="b93c7-145">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-145">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="b93c7-146">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-146">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="b93c7-147">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-147">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="b93c7-148">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-148">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a><span data-ttu-id="b93c7-149">Шаг 3. Включение локальной службы маркеров безопасности разработки для проверки подлинности пользователей</span><span class="sxs-lookup"><span data-stu-id="b93c7-149">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
 <span data-ttu-id="b93c7-150">В этом разделе описывается, как включить локальную службу маркеров безопасности разработки в приложении.</span><span class="sxs-lookup"><span data-stu-id="b93c7-150">This step describes how to enable Local Development STS in your application.</span></span> <span data-ttu-id="b93c7-151">Локальную службу маркеров безопасности разработки можно включить с помощью расширения для управления удостоверениями и доступом Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b93c7-151">Local Development STS is enabled by using the Identity and Access extension for Visual Studio.</span></span>  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a><span data-ttu-id="b93c7-152">Включение локальной службы маркеров безопасности разработки в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-152">To enable Local Development STS in your ASP.NET application</span></span>  
  
1.  <span data-ttu-id="b93c7-153">В Visual Studio щелкните правой кнопкой мыши проект **TestApp** в **обозревателе решений** и выберите элемент **Удостоверения и доступ**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-153">In Visual Studio, right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
2.  <span data-ttu-id="b93c7-154">Откроется окно **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-154">The **Identity and Access** window appears.</span></span> <span data-ttu-id="b93c7-155">В поле **Поставщики** выберите **Протестировать приложение с помощью локальной службы Development STS** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-155">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a><span data-ttu-id="b93c7-156">Шаг 4. Изменение приложения ASP.NET для отображения сведений о состоянии входа</span><span class="sxs-lookup"><span data-stu-id="b93c7-156">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
 <span data-ttu-id="b93c7-157">В этом разделе описывается, как изменить приложение ASP.NET для динамического отображения состояния входа текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b93c7-157">This step describes how to modify your ASP.NET application to dynamically display whether the current user is signed in.</span></span> <span data-ttu-id="b93c7-158">После настройки поставщика службы маркеров безопасности входящие утверждения обрабатываются платформой WIF.</span><span class="sxs-lookup"><span data-stu-id="b93c7-158">Once your STS provider has been configured, WIF handles the incoming claims.</span></span> <span data-ttu-id="b93c7-159">Теперь необходимо настроить код приложения, чтобы отображать результаты проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b93c7-159">Now you need to configure your application’s code to display the result of the authentication.</span></span>  
  
#### <a name="to-display-sign-in-status"></a><span data-ttu-id="b93c7-160">Отображение состояния входа</span><span class="sxs-lookup"><span data-stu-id="b93c7-160">To display sign in status</span></span>  
  
1.  <span data-ttu-id="b93c7-161">В Visual Studio откройте файл **Default.aspx** в проекте **TestApp**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-161">In Visual Studio, open the **Default.aspx** file under the **TestApp** project.</span></span>  
  
2.  <span data-ttu-id="b93c7-162">В файле **Default.aspx** замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="b93c7-162">Replace the existing markup in the **Default.aspx** file with the following markup:</span></span>  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  <span data-ttu-id="b93c7-163">Сохраните файл **Default.aspx**, а затем откройте его файл кода программной части с именем **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-163">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b93c7-164">Файл **Default.aspx.cs** может быть скрыт в узле **Default.aspx** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="b93c7-164">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="b93c7-165">Если файл **Default.aspx.cs** не отображается, разверните узел **Default.aspx**, щелкнув значок треугольника рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="b93c7-165">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
4.  <span data-ttu-id="b93c7-166">В файле **Default.aspx.cs** замените существующий код следующим:</span><span class="sxs-lookup"><span data-stu-id="b93c7-166">Replace the existing code in **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="b93c7-167">Сохраните файл **Default.aspx.cs** и выполните построение приложения.</span><span class="sxs-lookup"><span data-stu-id="b93c7-167">Save **Default.aspx.cs**, and build the application.</span></span>  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a><span data-ttu-id="b93c7-168">Шаг 5. Проверка интеграции между платформой WIF и приложением ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-168">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
 <span data-ttu-id="b93c7-169">В этом разделе описывается проверка интеграции между платформой WIF и приложением ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b93c7-169">This step describes how you can test the integration between WIF and your ASP.NET application.</span></span>  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a><span data-ttu-id="b93c7-170">Проверка интеграции между платформой WIF и приложением ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b93c7-170">To test the integration between WIF and ASP.NET</span></span>  
  
1.  <span data-ttu-id="b93c7-171">В Visual Studio нажмите клавишу **F5**, чтобы запустить отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="b93c7-171">In Visual Studio, press **F5** to start debugging your application.</span></span> <span data-ttu-id="b93c7-172">Если не будут обнаружены ошибки, откроется новое окно браузера.</span><span class="sxs-lookup"><span data-stu-id="b93c7-172">If no errors are found, a new browser window will open.</span></span>  
  
2.  <span data-ttu-id="b93c7-173">Обратите внимание, что браузер автоматически перенаправляет запрос к службе маркеров безопасности, после чего открывает страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b93c7-173">You may notice that the browser silently redirects your request to the STS, and then opens the Default.aspx page.</span></span> <span data-ttu-id="b93c7-174">Если платформа WIF правильно настроена, появится страница сайта с текстом **"Вход выполнен"**.</span><span class="sxs-lookup"><span data-stu-id="b93c7-174">If WIF is properly configured, you should see the site display the following text: **"You are signed in"**.</span></span>
