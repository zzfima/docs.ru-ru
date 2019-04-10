---
title: 'Как выполнить: Преобразование входящих утверждений'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: f836356125f1462f302b7e9f45a841c869c9a690
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344641"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="3414c-102">Как выполнить: Преобразование входящих утверждений</span><span class="sxs-lookup"><span data-stu-id="3414c-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="3414c-103">Применение</span><span class="sxs-lookup"><span data-stu-id="3414c-103">Applies To</span></span>  
  
-   <span data-ttu-id="3414c-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="3414c-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="3414c-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="3414c-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="3414c-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="3414c-106">Summary</span></span>  
 <span data-ttu-id="3414c-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET, поддерживающего утверждения, и преобразованию входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="3414c-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="3414c-108">Оно также содержит инструкции по тестированию приложения для проверки на наличие преобразованных утверждений во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="3414c-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="3414c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3414c-109">Contents</span></span>  
  
-   <span data-ttu-id="3414c-110">Цели</span><span class="sxs-lookup"><span data-stu-id="3414c-110">Objectives</span></span>  
  
-   <span data-ttu-id="3414c-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="3414c-111">Overview</span></span>  
  
-   <span data-ttu-id="3414c-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="3414c-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="3414c-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3414c-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="3414c-114">Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager</span><span class="sxs-lookup"><span data-stu-id="3414c-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="3414c-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="3414c-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="3414c-116">Цели</span><span class="sxs-lookup"><span data-stu-id="3414c-116">Objectives</span></span>  
  
-   <span data-ttu-id="3414c-117">Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="3414c-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="3414c-118">Преобразование входящих утверждений путем добавления утверждения роли администратора</span><span class="sxs-lookup"><span data-stu-id="3414c-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
-   <span data-ttu-id="3414c-119">Тестирование приложения веб-форм ASP.NET на правильность работы</span><span class="sxs-lookup"><span data-stu-id="3414c-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="3414c-120">Обзор</span><span class="sxs-lookup"><span data-stu-id="3414c-120">Overview</span></span>  
 <span data-ttu-id="3414c-121">WIF предоставляет класс с именем <xref:System.Security.Claims.ClaimsAuthenticationManager>, позволяющий пользователям изменять утверждения перед их представлением приложению проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="3414c-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="3414c-122"><xref:System.Security.Claims.ClaimsAuthenticationManager> полезен для разделения проблем между проверкой подлинности и базовым кодом приложения.</span><span class="sxs-lookup"><span data-stu-id="3414c-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="3414c-123">В приведенном ниже примере показано, как добавить роль в утверждения во входящем классе <xref:System.Security.Claims.ClaimsPrincipal>, который может потребоваться проверяющей стороне.</span><span class="sxs-lookup"><span data-stu-id="3414c-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="3414c-124">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="3414c-124">Summary of Steps</span></span>  
  
-   <span data-ttu-id="3414c-125">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3414c-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="3414c-126">Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager</span><span class="sxs-lookup"><span data-stu-id="3414c-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="3414c-127">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="3414c-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="3414c-128">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3414c-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="3414c-129">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3414c-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="3414c-130">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3414c-130">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="3414c-131">Запустите Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3414c-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="3414c-132">В Visual Studio в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="3414c-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="3414c-133">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="3414c-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4. <span data-ttu-id="3414c-134">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3414c-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5. <span data-ttu-id="3414c-135">В **обозревателе решений** щелкните правой кнопкой мыши проект **TestApp**, а затем выберите **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="3414c-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6. <span data-ttu-id="3414c-136">Откроется окно **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="3414c-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="3414c-137">В поле **Поставщики** выберите **Протестировать приложение с помощью локальной службы Development STS** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="3414c-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7. <span data-ttu-id="3414c-138">В файле *Default.aspx* замените существующую разметку приведенной ниже, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="3414c-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
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
  
8. <span data-ttu-id="3414c-139">Откройте файл кода программной части с именем *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="3414c-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="3414c-140">Замените существующий код приведенным ниже, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="3414c-140">Replace the existing code with the following, then save the file:</span></span>  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="3414c-141">Шаг 2. Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager</span><span class="sxs-lookup"><span data-stu-id="3414c-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="3414c-142">На этом шаге переопределяются функциональные возможности по умолчанию в классе <xref:System.Security.Claims.ClaimsAuthenticationManager> для добавления роли администратора во входящий субъект.</span><span class="sxs-lookup"><span data-stu-id="3414c-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="3414c-143">Реализация преобразования утверждений с помощью настраиваемого ClaimsAuthenticationManager</span><span class="sxs-lookup"><span data-stu-id="3414c-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1. <span data-ttu-id="3414c-144">В Visual Studio щелкните решение правой кнопкой мыши, выберите команду **Добавить** и пункт **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="3414c-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="3414c-145">В окне **Добавление нового проекта** выберите **Библиотека классов** в списке шаблонов **Visual C#**, введите `ClaimsTransformation` и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3414c-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="3414c-146">В папке решения будет создан новый проект.</span><span class="sxs-lookup"><span data-stu-id="3414c-146">The new project will be created in your solution folder.</span></span>  
  
3. <span data-ttu-id="3414c-147">Щелкните правой кнопкой мыши элемент **Ссылки** в проекте **ClaimsTransformation** и выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="3414c-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4. <span data-ttu-id="3414c-148">В окне **Диспетчер ссылок** выберите **System.IdentityModel**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3414c-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="3414c-149">Откройте **Class1.cs**, или если он не существует, щелкните правой кнопкой мыши **ClaimsTransformation**, выберите **Добавить** и щелкните **Класс...**</span><span class="sxs-lookup"><span data-stu-id="3414c-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6. <span data-ttu-id="3414c-150">В файл кода добавьте следующие директивы using:</span><span class="sxs-lookup"><span data-stu-id="3414c-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7. <span data-ttu-id="3414c-151">В файл кода добавьте следующий класс и метод.</span><span class="sxs-lookup"><span data-stu-id="3414c-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="3414c-152">Следующий код приведен исключительно для демонстрации. Проверьте нужные разрешения в рабочем коде.</span><span class="sxs-lookup"><span data-stu-id="3414c-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
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
  
8. <span data-ttu-id="3414c-153">Сохраните файл и выполните сборку проекта **ClaimsTransformation**.</span><span class="sxs-lookup"><span data-stu-id="3414c-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="3414c-154">В проекте ASP.NET **TestApp** щелкните правой кнопкой мыши "Ссылки", а затем выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="3414c-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="3414c-155">В окне **Диспетчер ссылок** в левом меню выберите **Решения**, в заполненных параметрах выберите **ClaimsTransformation**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3414c-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="3414c-156">В корневом файле **Web.config** перейдите к записи **\<system.identityModel>**.</span><span class="sxs-lookup"><span data-stu-id="3414c-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="3414c-157">В элементах **\<identityConfiguration>** добавьте следующую строку и сохраните файл:</span><span class="sxs-lookup"><span data-stu-id="3414c-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="3414c-158">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="3414c-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="3414c-159">На этом шаге тестируется приложение веб-форм ASP.NET и проверяется наличие утверждений при входе пользователя с помощью проверки подлинности на основе форм.</span><span class="sxs-lookup"><span data-stu-id="3414c-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="3414c-160">Тестирование приложения веб-форм ASP.NET на наличие утверждений с использованием проверки подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="3414c-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1. <span data-ttu-id="3414c-161">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="3414c-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="3414c-162">Откроется страница *Default.aspx*.</span><span class="sxs-lookup"><span data-stu-id="3414c-162">You should be presented with *Default.aspx*.</span></span>  
  
2. <span data-ttu-id="3414c-163">На странице *Default.aspx* вы увидите таблицу под заголовком **Ваши утверждения**, содержащую сведения утверждений **Issuer**, **OriginalIssuer**, **Type**, **Value** и **ValueType** о вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3414c-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="3414c-164">Последняя строка должна иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="3414c-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="3414c-165">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="3414c-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="3414c-166">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="3414c-166">LOCAL AUTHORITY</span></span>|`http://schemas.microsoft.com/ws/2008/06/identity/claims/role`|<span data-ttu-id="3414c-167">Администратор</span><span class="sxs-lookup"><span data-stu-id="3414c-167">Admin</span></span>|<https://www.w3.org/2001/XMLSchema#string>|
