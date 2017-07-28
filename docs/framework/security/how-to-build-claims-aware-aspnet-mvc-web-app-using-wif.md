---
title: "Практическое руководство. Создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с помощью WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Практическое руководство. Создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с помощью WIF
## Применение  
  
-   Основой идентификатора Microsoft® Windows® \(WIF\)  
  
-   ASP.NET® MVC  
  
## Сводка  
 Это предоставляет подробные пошаговые процедуры по созданию простого утверждение\- осведомленное веб\-приложения MVC ASP.NET.  Он также предоставляет инструкции, как проверка простого утверждение\- осведомленное веб\-приложения ASP.NET MVC для успешной реализации проверки подлинности на основе утверждений.  Это называется не содержит подробные инструкции по созданию службы маркеров безопасности \(sts\), и предполагается, что вы уже настроены службы маркеров безопасности.  
  
## Содержимое  
  
-   Назначения  
  
-   Сводка шагов  
  
-   Шаг 1. создание простого приложения ASP.NET MVC  
  
-   Шаг 2. настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
-   Шаг 3 \- теста решение  
  
-   Связанные элементы  
  
## Назначения  
  
-   Настройка веб\-приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
-   Проверьте успешное утверждение\- осведомленное веб\-приложения ASP.NET MVC  
  
## Сводка шагов  
  
-   Шаг 1. создание простого приложения ASP.NET MVC  
  
-   Шаг 2. настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
-   Шаг 3 \- теста решение  
  
## Шаг 1. создание простого приложения ASP.NET MVC  
 На этом шаге создается новое приложение MVC ASP.NET.  
  
#### Создать простое приложение ASP.NET MVC  
  
1.  Запустите Visual Studio и щелкните **Файл**, **Создать**, а затем **Проект**.  
  
2.  В окне **Создать проект**, нажмите кнопку **Веб\-приложение ASP.NET MVC 3**.  
  
3.  В **Имя** введите `TestApp` и нажмите клавишу **ОК**.  
  
4.  В диалоговом окне **Создание проекта ASP.NET MVC 3** выберите **Веб\-приложение** из доступных шаблонов, убедитесь, что **Просмотр обработчика** установлено в **бритва** и нажмите кнопку **ОК**.  
  
5.  Если новый проект откроется, щелкните правой кнопкой мыши проект **TestApp** в **Обозреватель решений** и выберите параметр **Свойства**.  
  
6.  На странице свойств проекта, щелкните вкладку **Интернет** в левом и убедитесь, что параметр **Используйте локальный веб\-сервер IIS** выбрать.  
  
## Шаг 2. настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
 На этом этапе добавлении записи конфигурации в *файл конфигурации Web.config* веб\-приложения ASP.NET MVC сделать его утверждение\- с учетом.  
  
#### Настройка приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
1.  Добавьте следующие определения раздела конфигурации в *файл конфигурации Web.config*.  Они определяют разделы конфигурации, необходимые учредительством идентификатора Windows.  Добавление определения сразу **\<configuration\>** после элемента:  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Добавьте элемент **\<location\>**, который разрешает доступ к метаданным федерации приложения:  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  Добавьте следующие записи конфигурации внутри элементов **\<system.web\>** для отключения пользователей, отключите собственной проверки подлинности и разрешить WIF для управления проверка подлинности.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Добавьте следующие записи конфигурации идентификатора Windows, связанных учредительством и убедитесь, что URL\-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris\>**, атрибуте **область** элемента **\<wsFederation\>** и атрибуте **ответ** элемента **\<wsFederation\>**.  Также убедитесь в том, что значение **Поставщик** соответствия в URL\-адрес службы маркеров безопасности \(sts\).  
  
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
  
5.  Добавьте ссылку на сборку [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True).  
  
6.  Компилирование решение, чтобы убедиться, что ошибки.  
  
## Шаг 3 \- теста решение  
 На этом шаге вы проверяете ваше настроенное веб\-приложения ASP.NET MVC для проверки подлинности на основе утверждений.  Выполнение простой тест можно добавить простой код, который показывает утверждения в токене выданного службой маркеров безопасности \(sts\).  
  
#### Тестирования приложения ASP.NET MVC для проверки подлинности на основе утверждений  
  
1.  В **Обозреватель решений** разверните папку**Контроллеры** и откройте *HomeController.cs* в редакторе.  Добавьте следующий код в метод **Индекс**:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
  
    ```  
  
2.  В **Обозреватель решений** разверните папки **Представления** а затем **Главная** и откройте файл *Index.cshtml* в редакторе.  Удалите ее содержимое и добавьте следующую разметку:  
  
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
  
3.  Запустите решение, нажав клавиши ключ **F5**.  
  
4.  Необходимо со страницей, показывающая утверждения в токене, который был выдан возможность службой маркеров безопасности.  
  
## Связанные элементы  
  
-   [Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)