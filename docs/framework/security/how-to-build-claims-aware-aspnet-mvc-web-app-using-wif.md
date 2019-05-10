---
title: 'Как выполнить: создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
ms.openlocfilehash: f2ac263d8869c770594283923a45c7c53c9df4cb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626122"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a>Как выполнить: создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF
## <a name="applies-to"></a>Применение  
  
- Microsoft® Windows® Identity Foundation (WIF)  
  
- ASP.NET® MVC  
  
## <a name="summary"></a>Сводка  
 В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого веб-приложения ASP.NET MVC с поддержкой утверждений. Также здесь приводятся инструкции по тестированию простого веб-приложения ASP.NET MVC с поддержкой утверждений для реализации проверки подлинности на основе утверждений. В этом практическом руководстве не приводятся подробные инструкции по созданию службы маркеров безопасности (STS) и подразумевается, что вы уже выполнили ее настройку.  
  
## <a name="contents"></a>Описание  
  
- Цели  
  
- Сводка действий  
  
- Шаг 1. Создание простого приложения ASP.NET MVC  
  
- Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
- Шаг 3. Тестирование решения  
  
- Связанные элементы:  
  
## <a name="objectives"></a>Цели  
  
- Настройка веб-приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
- Тестирование веб-приложения ASP.NET MVC с поддержкой утверждений  
  
## <a name="summary-of-steps"></a>Сводка действий  
  
- Шаг 1. Создание простого приложения ASP.NET MVC  
  
- Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
- Шаг 3. Тестирование решения  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a>Шаг 1. Создание простого приложения ASP.NET MVC  
 На этом шаге создается новое приложение ASP.NET MVC.  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a>Создание простого приложения ASP.NET MVC  
  
1. Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.  
  
2. В окне **Новый проект** выберите **Веб-приложение ASP.NET MVC 3**.  
  
3. В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.  
  
4. В диалоговом окне **Создание проекта ASP.NET MVC 3** выберите шаблон **Интернет-приложение** в списке доступных. Затем убедитесь, что для параметра **Обработчик представлений** задано значение **Razor**, после чего нажмите кнопку **ОК**.  
  
5. После открытия нового проекта щелкните правой кнопкой мыши проект **TestApp** в **обозревателе решений** и выберите параметр **Свойства**.  
  
6. На странице свойств проекта откройте вкладку **Интернет** слева и убедитесь, что выбран параметр **Использовать локальный веб-сервер IIS**.  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a>Шаг 2. Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
 На этом шаге в файл конфигурации *Web.config* веб-приложения ASP.NET MVC добавляются записи конфигурации, позволяющие реализовать поддержку утверждений.  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a>Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
1. Добавьте в файл конфигурации *Web.config* следующие определения разделов конфигурации. Они определяют разделы конфигурации, которые используются платформой Windows Identity Foundation. Определения необходимо добавлять непосредственно после открывающего элемента **\<configuration>**:  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2. Добавьте элемент **\<location>**, который обеспечивает доступ к метаданным федерации приложения:  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3. Добавьте следующие записи конфигурации в элементы **\<system.web>**, чтобы запретить пользователей, отключить собственную проверку подлинности и включить платформу WIF для управления проверкой подлинности.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4. Добавьте следующие записи конфигурации платформы Windows Identity Foundation и убедитесь, что URL-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris>**, атрибуте **realm** элемента **\<wsFederation>** и атрибуте **reply** элемента **\<wsFederation>**. Также убедитесь, что значение **issuer** соответствует URL-адресу службы маркеров безопасности (STS).  
  
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
  
5. Добавьте ссылку на сборку <xref:System.IdentityModel>.  
  
6. Скомпилируйте решение и убедитесь в отсутствии ошибок.  
  
## <a name="step-3--test-your-solution"></a>Шаг 3. Тестирование решения  
 На этом шаге выполняется тестирование веб-приложения ASP.NET MVC, настроенного для проверки подлинности на основе утверждений. Для базовой проверки необходимо добавить простой код, который отображает утверждения в маркере безопасности, выданном службой STS.  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a>Тестирование приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
1. В **обозревателе решений** разверните папку **Контроллеры** и откройте файл *HomeController.cs* в редакторе. Добавьте следующий код в метод **Index**:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2. В **обозревателе решений** разверните папки **Представления** и **Главная**, после чего откройте файл *Index.cshtml* в редакторе. Удалите его содержимое и добавьте следующую разметку:  
  
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
  
3. Запустите решение, нажав клавишу **F5**.  
  
4. Появится страница, на которой будут отображены утверждения в маркере безопасности, выданном службой маркеров безопасности.  
  
## <a name="related-items"></a>Связанные элементы:  
  
- [Практическое руководство. Создание приложения с поддержкой утверждений ASP.NET Web Forms, с помощью WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
