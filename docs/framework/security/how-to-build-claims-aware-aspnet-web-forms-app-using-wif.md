---
title: Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 764e7fba31a7fb3fc40ec85ab4d0fb6e18e57390
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931776"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="0704d-102">Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF</span><span class="sxs-lookup"><span data-stu-id="0704d-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="0704d-103">Применение</span><span class="sxs-lookup"><span data-stu-id="0704d-103">Applies To</span></span>  
  
-   <span data-ttu-id="0704d-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="0704d-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="0704d-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="0704d-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="0704d-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="0704d-106">Summary</span></span>  
 <span data-ttu-id="0704d-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений.</span><span class="sxs-lookup"><span data-stu-id="0704d-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="0704d-108">Также здесь приводятся инструкции по тестированию простого приложения веб-форм ASP.NET с поддержкой утверждений для реализации федеративной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0704d-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="0704d-109">В этом практическом руководстве не приводятся подробные инструкции по созданию службы маркеров безопасности (STS) и подразумевается, что вы уже выполнили ее настройку.</span><span class="sxs-lookup"><span data-stu-id="0704d-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="0704d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0704d-110">Contents</span></span>  
  
-   <span data-ttu-id="0704d-111">Цели</span><span class="sxs-lookup"><span data-stu-id="0704d-111">Objectives</span></span>  
  
-   <span data-ttu-id="0704d-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="0704d-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="0704d-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0704d-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="0704d-114">Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="0704d-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="0704d-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="0704d-116">Цели</span><span class="sxs-lookup"><span data-stu-id="0704d-116">Objectives</span></span>  
  
-   <span data-ttu-id="0704d-117">Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="0704d-118">Тестирование приложения веб-форм ASP.NET с поддержкой утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="0704d-119">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="0704d-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="0704d-120">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0704d-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="0704d-121">Шаг 2. Настройка приложения веб-форм ASP.NET для федеративной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0704d-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
-   <span data-ttu-id="0704d-122">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="0704d-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="0704d-123">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0704d-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="0704d-124">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0704d-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="0704d-125">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0704d-125">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="0704d-126">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0704d-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="0704d-127">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="0704d-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="0704d-128">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0704d-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="0704d-129">Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="0704d-130">На этом шаге в файл конфигурации *Web.config* приложения веб-форм ASP.NET добавляются записи конфигурации, позволяющие реализовать поддержку утверждений.</span><span class="sxs-lookup"><span data-stu-id="0704d-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="0704d-131">Настройка приложения ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="0704d-132">Добавьте в файл конфигурации *Web.config* следующий раздел конфигурации непосредственно после открывающего элемента **\<configuration>**:</span><span class="sxs-lookup"><span data-stu-id="0704d-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="0704d-133">Добавьте элемент **\<location>**, который обеспечивает доступ к метаданным федерации приложения:</span><span class="sxs-lookup"><span data-stu-id="0704d-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="0704d-134">Добавьте следующие записи конфигурации в элементы **\<system.web>**, чтобы запретить пользователей, отключить собственную проверку подлинности и включить платформу WIF для управления проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="0704d-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="0704d-135">Добавьте элемент **\<system.webServer>**, который определяет модули для федеративной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0704d-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="0704d-136">Обратите внимание, что атрибут *PublicKeyToken* должен иметь то же значение, что и атрибут *PublicKeyToken* для ранее добавленных записей **\<configSections>**:</span><span class="sxs-lookup"><span data-stu-id="0704d-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  <span data-ttu-id="0704d-137">Добавьте следующие записи конфигурации платформы Windows Identity Foundation и убедитесь, что URL-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris>**, атрибуте **realm** элемента **\<wsFederation>** и атрибуте **reply** элемента **\<wsFederation>**.</span><span class="sxs-lookup"><span data-stu-id="0704d-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="0704d-138">Также убедитесь, что значение **issuer** соответствует URL-адресу службы маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="0704d-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="true" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="true" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  <span data-ttu-id="0704d-139">Добавьте ссылку на сборку <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="0704d-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7.  <span data-ttu-id="0704d-140">Скомпилируйте решение и убедитесь в отсутствии ошибок.</span><span class="sxs-lookup"><span data-stu-id="0704d-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="0704d-141">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="0704d-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="0704d-142">На этом шаге выполняется тестирование приложения веб-форм ASP.NET, настроенного для проверки подлинности на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="0704d-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="0704d-143">Для базовой проверки необходимо добавить код, который отображает утверждения в маркере безопасности, выданном службой STS.</span><span class="sxs-lookup"><span data-stu-id="0704d-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="0704d-144">Проверка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="0704d-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="0704d-145">Откройте файл **Default.aspx** в проекте **TestApp** и замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="0704d-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  <span data-ttu-id="0704d-146">Сохраните файл **Default.aspx**, а затем откройте его файл кода программной части с именем **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="0704d-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0704d-147">Файл **Default.aspx.cs** может быть скрыт в узле **Default.aspx** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="0704d-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="0704d-148">Если файл **Default.aspx.cs** не отображается, разверните узел **Default.aspx**, щелкнув значок треугольника рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="0704d-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3.  <span data-ttu-id="0704d-149">Замените существующий код метода **Page_Load** в файле **Default.aspx.cs** следующим:</span><span class="sxs-lookup"><span data-stu-id="0704d-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="0704d-150">Сохраните файл **Default.aspx.cs** и выполните построение решения.</span><span class="sxs-lookup"><span data-stu-id="0704d-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5.  <span data-ttu-id="0704d-151">Запустите решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="0704d-151">Run the solution by pressing the **F5** key.</span></span>  
  
6.  <span data-ttu-id="0704d-152">Появится страница, на которой будут отображены утверждения в маркере безопасности, выданном службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="0704d-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>
