---
title: 'Как выполнить: создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
ms.openlocfilehash: 04861b8c3f2673a5cd093be1351928b1da487147
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335671"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a><span data-ttu-id="fbe04-102">Как выполнить: создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF</span><span class="sxs-lookup"><span data-stu-id="fbe04-102">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="fbe04-103">Применение</span><span class="sxs-lookup"><span data-stu-id="fbe04-103">Applies To</span></span>  
  
-   <span data-ttu-id="fbe04-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="fbe04-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="fbe04-105">ASP.NET® MVC</span><span class="sxs-lookup"><span data-stu-id="fbe04-105">ASP.NET® MVC</span></span>  
  
## <a name="summary"></a><span data-ttu-id="fbe04-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="fbe04-106">Summary</span></span>  
 <span data-ttu-id="fbe04-107">В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого веб-приложения ASP.NET MVC с поддержкой утверждений.</span><span class="sxs-lookup"><span data-stu-id="fbe04-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET MVC web application.</span></span> <span data-ttu-id="fbe04-108">Также здесь приводятся инструкции по тестированию простого веб-приложения ASP.NET MVC с поддержкой утверждений для реализации проверки подлинности на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="fbe04-108">It also provides instructions how to test the simple claims-aware ASP.NET MVC web application for successful implementation of claims-based authentication.</span></span> <span data-ttu-id="fbe04-109">В этом практическом руководстве не приводятся подробные инструкции по созданию службы маркеров безопасности (STS) и подразумевается, что вы уже выполнили ее настройку.</span><span class="sxs-lookup"><span data-stu-id="fbe04-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="fbe04-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fbe04-110">Contents</span></span>  
  
-   <span data-ttu-id="fbe04-111">Цели</span><span class="sxs-lookup"><span data-stu-id="fbe04-111">Objectives</span></span>  
  
-   <span data-ttu-id="fbe04-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="fbe04-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="fbe04-113">Шаг 1. Создание простого приложения ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="fbe04-113">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="fbe04-114">Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-114">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="fbe04-115">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="fbe04-115">Step 3 – Test Your Solution</span></span>  
  
-   <span data-ttu-id="fbe04-116">Связанные элементы:</span><span class="sxs-lookup"><span data-stu-id="fbe04-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="fbe04-117">Цели</span><span class="sxs-lookup"><span data-stu-id="fbe04-117">Objectives</span></span>  
  
-   <span data-ttu-id="fbe04-118">Настройка веб-приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-118">Configure ASP.NET MVC web application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="fbe04-119">Тестирование веб-приложения ASP.NET MVC с поддержкой утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-119">Test successful claims-aware ASP.NET MVC web application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="fbe04-120">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="fbe04-120">Summary of Steps</span></span>  
  
-   <span data-ttu-id="fbe04-121">Шаг 1. Создание простого приложения ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="fbe04-121">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="fbe04-122">Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-122">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="fbe04-123">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="fbe04-123">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a><span data-ttu-id="fbe04-124">Шаг 1. Создание простого приложения ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="fbe04-124">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
 <span data-ttu-id="fbe04-125">На этом шаге создается новое приложение ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="fbe04-125">In this step, you will create a new ASP.NET MVC application.</span></span>  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a><span data-ttu-id="fbe04-126">Создание простого приложения ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="fbe04-126">To create simple ASP.NET MVC application</span></span>  
  
1. <span data-ttu-id="fbe04-127">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-127">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="fbe04-128">В окне **Новый проект** выберите **Веб-приложение ASP.NET MVC 3**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-128">In the **New Project** window, click **ASP.NET MVC 3 Web Application**.</span></span>  
  
3. <span data-ttu-id="fbe04-129">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-129">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="fbe04-130">В диалоговом окне **Создание проекта ASP.NET MVC 3** выберите шаблон **Интернет-приложение** в списке доступных. Затем убедитесь, что для параметра **Обработчик представлений** задано значение **Razor**, после чего нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-130">In the **New ASP.NET MVC 3 Project** dialog, select **Internet Application** from the available templates, ensure **View Engine** is set to **Razor**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="fbe04-131">После открытия нового проекта щелкните правой кнопкой мыши проект **TestApp** в **обозревателе решений** и выберите параметр **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-131">When the new project opens, right-click the **TestApp** project in **Solution Explorer** and select the **Properties** option.</span></span>  
  
6. <span data-ttu-id="fbe04-132">На странице свойств проекта откройте вкладку **Интернет** слева и убедитесь, что выбран параметр **Использовать локальный веб-сервер IIS**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-132">On the project’s properties page, click on the **Web** tab on the left and ensure that the **Use Local IIS Web Server** option is selected.</span></span>  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="fbe04-133">Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-133">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="fbe04-134">На этом шаге в файл конфигурации *Web.config* веб-приложения ASP.NET MVC добавляются записи конфигурации, позволяющие реализовать поддержку утверждений.</span><span class="sxs-lookup"><span data-stu-id="fbe04-134">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET MVC web application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="fbe04-135">Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-135">To configure ASP.NET MVC application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="fbe04-136">Добавьте в файл конфигурации *Web.config* следующие определения разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fbe04-136">Add the following configuration section definitions to the *Web.config* configuration file.</span></span> <span data-ttu-id="fbe04-137">Они определяют разделы конфигурации, которые используются платформой Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="fbe04-137">These define configuration sections required by Windows Identity Foundation.</span></span> <span data-ttu-id="fbe04-138">Определения необходимо добавлять непосредственно после открывающего элемента **\<configuration>**:</span><span class="sxs-lookup"><span data-stu-id="fbe04-138">Add the definitions immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2. <span data-ttu-id="fbe04-139">Добавьте элемент **\<location>**, который обеспечивает доступ к метаданным федерации приложения:</span><span class="sxs-lookup"><span data-stu-id="fbe04-139">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3. <span data-ttu-id="fbe04-140">Добавьте следующие записи конфигурации в элементы **\<system.web>**, чтобы запретить пользователей, отключить собственную проверку подлинности и включить платформу WIF для управления проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="fbe04-140">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4. <span data-ttu-id="fbe04-141">Добавьте следующие записи конфигурации платформы Windows Identity Foundation и убедитесь, что URL-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris>**, атрибуте **realm** элемента **\<wsFederation>** и атрибуте **reply** элемента **\<wsFederation>**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-141">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="fbe04-142">Также убедитесь, что значение **issuer** соответствует URL-адресу службы маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="fbe04-142">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5. <span data-ttu-id="fbe04-143">Добавьте ссылку на сборку <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="fbe04-143">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
6. <span data-ttu-id="fbe04-144">Скомпилируйте решение и убедитесь в отсутствии ошибок.</span><span class="sxs-lookup"><span data-stu-id="fbe04-144">Compile the solution to make sure there are errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="fbe04-145">Шаг 3. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="fbe04-145">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="fbe04-146">На этом шаге выполняется тестирование веб-приложения ASP.NET MVC, настроенного для проверки подлинности на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="fbe04-146">In this step you will test your ASP.NET MVC web application configured for claims-based authentication.</span></span> <span data-ttu-id="fbe04-147">Для базовой проверки необходимо добавить простой код, который отображает утверждения в маркере безопасности, выданном службой STS.</span><span class="sxs-lookup"><span data-stu-id="fbe04-147">To perform basic test you will add simple code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="fbe04-148">Тестирование приложения ASP.NET MVC для проверки подлинности на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="fbe04-148">To test your ASP.NET MVC application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="fbe04-149">В **обозревателе решений** разверните папку **Контроллеры** и откройте файл *HomeController.cs* в редакторе.</span><span class="sxs-lookup"><span data-stu-id="fbe04-149">In the **Solution Explorer**, expand the **Controllers** folder and open *HomeController.cs* file in the editor.</span></span> <span data-ttu-id="fbe04-150">Добавьте следующий код в метод **Index**:</span><span class="sxs-lookup"><span data-stu-id="fbe04-150">Add the following code to the **Index** method:</span></span>  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2. <span data-ttu-id="fbe04-151">В **обозревателе решений** разверните папки **Представления** и **Главная**, после чего откройте файл *Index.cshtml* в редакторе.</span><span class="sxs-lookup"><span data-stu-id="fbe04-151">In the **Solution Explorer** expand **Views** and then **Home** folders and open *Index.cshtml* file in the editor.</span></span> <span data-ttu-id="fbe04-152">Удалите его содержимое и добавьте следующую разметку:</span><span class="sxs-lookup"><span data-stu-id="fbe04-152">Delete its contents and add the following markup:</span></span>  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3. <span data-ttu-id="fbe04-153">Запустите решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="fbe04-153">Run the solution by pressing the **F5** key.</span></span>  
  
4. <span data-ttu-id="fbe04-154">Появится страница, на которой будут отображены утверждения в маркере безопасности, выданном службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="fbe04-154">You should be presented with the page that displays the claims in the token that was issued to you by Security Token Service.</span></span>  
  
## <a name="related-items"></a><span data-ttu-id="fbe04-155">Связанные элементы:</span><span class="sxs-lookup"><span data-stu-id="fbe04-155">Related Items</span></span>  
  
-   [<span data-ttu-id="fbe04-156">Как выполнить: создание приложения ASP.NET Web Forms, поддерживающего утверждения, с использованием WIF</span><span class="sxs-lookup"><span data-stu-id="fbe04-156">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
