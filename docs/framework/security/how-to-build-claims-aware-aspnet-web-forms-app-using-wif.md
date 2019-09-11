---
title: Как создание приложения ASP.NET Web Forms, поддерживающего утверждения, с использованием WIF
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
ms.openlocfilehash: 45ad084013cbcafdf0d7c4ac3e0fd952305232c4
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851557"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="18957-102">Как создание приложения ASP.NET Web Forms, поддерживающего утверждения, с использованием WIF</span><span class="sxs-lookup"><span data-stu-id="18957-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="18957-103">Применение</span><span class="sxs-lookup"><span data-stu-id="18957-103">Applies To</span></span>  
  
- <span data-ttu-id="18957-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="18957-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="18957-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="18957-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="18957-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="18957-106">Summary</span></span>  
 <span data-ttu-id="18957-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений.</span><span class="sxs-lookup"><span data-stu-id="18957-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="18957-108">Также здесь приводятся инструкции по тестированию простого приложения веб-форм ASP.NET с поддержкой утверждений для реализации федеративной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="18957-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="18957-109">В этом практическом руководстве не приводятся подробные инструкции по созданию службы маркеров безопасности (STS) и подразумевается, что вы уже выполнили ее настройку.</span><span class="sxs-lookup"><span data-stu-id="18957-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="18957-110">Описание</span><span class="sxs-lookup"><span data-stu-id="18957-110">Contents</span></span>  
  
- <span data-ttu-id="18957-111">Цели</span><span class="sxs-lookup"><span data-stu-id="18957-111">Objectives</span></span>  
  
- <span data-ttu-id="18957-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="18957-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="18957-113">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18957-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="18957-114">Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
- <span data-ttu-id="18957-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="18957-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="18957-116">Цели</span><span class="sxs-lookup"><span data-stu-id="18957-116">Objectives</span></span>  
  
- <span data-ttu-id="18957-117">Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
- <span data-ttu-id="18957-118">Тестирование приложения веб-форм ASP.NET с поддержкой утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="18957-119">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="18957-119">Summary of Steps</span></span>  
  
- <span data-ttu-id="18957-120">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18957-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="18957-121">Шаг 2. Настройка приложения веб-форм ASP.NET для федеративной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="18957-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
- <span data-ttu-id="18957-122">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="18957-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="18957-123">Шаг 1. Создание простого приложения веб-форм ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18957-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="18957-124">На этом шаге создается новое приложение веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="18957-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="18957-125">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18957-125">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="18957-126">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="18957-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="18957-127">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="18957-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="18957-128">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="18957-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="18957-129">Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="18957-130">На этом шаге в файл конфигурации *Web.config* приложения веб-форм ASP.NET добавляются записи конфигурации, позволяющие реализовать поддержку утверждений.</span><span class="sxs-lookup"><span data-stu-id="18957-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="18957-131">Настройка приложения ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="18957-132">Добавьте в файл конфигурации *Web.config* следующий раздел конфигурации непосредственно после открывающего элемента **\<configuration>** :</span><span class="sxs-lookup"><span data-stu-id="18957-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2. <span data-ttu-id="18957-133">Добавьте элемент **\<location>** , который обеспечивает доступ к метаданным федерации приложения:</span><span class="sxs-lookup"><span data-stu-id="18957-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3. <span data-ttu-id="18957-134">Добавьте следующие записи конфигурации в элементы **\<system.web>** , чтобы запретить пользователей, отключить собственную проверку подлинности и включить платформу WIF для управления проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="18957-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4. <span data-ttu-id="18957-135">Добавьте элемент **\<system.webServer>** , который определяет модули для федеративной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="18957-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="18957-136">Обратите внимание, что атрибут *PublicKeyToken* должен иметь то же значение, что и атрибут *PublicKeyToken* для ранее добавленных записей **\<configSections>** :</span><span class="sxs-lookup"><span data-stu-id="18957-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5. <span data-ttu-id="18957-137">Добавьте следующие записи конфигурации платформы Windows Identity Foundation и убедитесь, что URL-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris>** , атрибуте **realm** элемента **\<wsFederation>** и атрибуте **reply** элемента **\<wsFederation>** .</span><span class="sxs-lookup"><span data-stu-id="18957-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="18957-138">Также убедитесь, что значение **issuer** соответствует URL-адресу службы маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="18957-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
  
6. <span data-ttu-id="18957-139">Добавьте ссылку на сборку <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="18957-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7. <span data-ttu-id="18957-140">Скомпилируйте решение и убедитесь в отсутствии ошибок.</span><span class="sxs-lookup"><span data-stu-id="18957-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="18957-141">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="18957-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="18957-142">На этом шаге выполняется тестирование приложения веб-форм ASP.NET, настроенного для проверки подлинности на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="18957-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="18957-143">Для базовой проверки необходимо добавить код, который отображает утверждения в маркере безопасности, выданном службой STS.</span><span class="sxs-lookup"><span data-stu-id="18957-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="18957-144">Проверка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="18957-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="18957-145">Откройте файл **Default.aspx** в проекте **TestApp** и замените существующую разметку следующей:</span><span class="sxs-lookup"><span data-stu-id="18957-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```aspx-csharp
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
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
  
2. <span data-ttu-id="18957-146">Сохраните файл **Default.aspx**, а затем откройте его файл кода программной части с именем **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="18957-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="18957-147">Файл **Default.aspx.cs** может быть скрыт в узле **Default.aspx** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="18957-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="18957-148">Если файл **Default.aspx.cs** не отображается, разверните узел **Default.aspx**, щелкнув значок треугольника рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="18957-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3. <span data-ttu-id="18957-149">Замените существующий код метода **Page_Load** в файле **Default.aspx.cs** следующим:</span><span class="sxs-lookup"><span data-stu-id="18957-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
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
  
4. <span data-ttu-id="18957-150">Сохраните файл **Default.aspx.cs** и выполните построение решения.</span><span class="sxs-lookup"><span data-stu-id="18957-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5. <span data-ttu-id="18957-151">Запустите решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="18957-151">Run the solution by pressing the **F5** key.</span></span>  
  
6. <span data-ttu-id="18957-152">Появится страница, на которой будут отображены утверждения в маркере безопасности, выданном службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="18957-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>
