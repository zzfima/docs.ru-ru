---
title: "Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF
## Применение  
  
-   Основой идентификатора Microsoft® Windows® \(WIF\)  
  
-   Веб\-формы ASP.NET®  
  
## Сводка  
 Это предоставляет подробные пошаговые процедуры по созданию простого утверждение\- осведомленное приложение веб\-формы ASP.NET.  Он также предоставляет инструкции для проверки утверждение\- осведомленное как простое приложение веб\-формы ASP.NET для успешной реализации федеративной проверки подлинности.  Это называется не содержит подробные инструкции по созданию службы маркеров безопасности \(sts\), и предполагается, что вы уже настроены службы маркеров безопасности.  
  
## Содержимое  
  
-   Назначения  
  
-   Сводка шагов  
  
-   Шаг 1. создание простого приложения веб\-форм ASP.NET  
  
-   Шаг 2. настройка приложения веб\-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Шаг 3 \- теста решение  
  
## Назначения  
  
-   Настройка приложения веб\-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Проверьте успешное утверждение\- осведомленное приложения веб\-форм ASP.NET  
  
## Сводка шагов  
  
-   Шаг 1. создание простого приложения веб\-форм ASP.NET  
  
-   Шаг 2. настройка приложения веб\-форм ASP.NET для федеративной проверки подлинности  
  
-   Шаг 3 \- теста решение  
  
## Шаг 1. создание простого приложения веб\-форм ASP.NET  
 На этом шаге создается новое приложение веб\-формы ASP.NET.  
  
#### Создать простое приложение ASP.NET  
  
1.  Запустите Visual Studio и щелкните **Файл**, **Создать**, а затем **Проект**.  
  
2.  В окне **Создать проект**, нажмите кнопку **приложение веб\-формы ASP.NET**.  
  
3.  В **Имя** введите `TestApp` и нажмите клавишу **ОК**.  
  
## Шаг 2. настройка приложения веб\-форм ASP.NET для проверки подлинности на основе утверждений  
 На этом этапе добавлении записи конфигурации в *файл конфигурации Web.config* приложения веб\-форм ASP.NET делает его утверждение\- осведомленной.  
  
#### Настройка приложения ASP.NET для проверки подлинности на основе утверждений  
  
1.  Добавьте следующие записи раздела конфигурации в *файл конфигурации Web.config* сразу после элемента **\<configuration\>**:  
  
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
  
4.  Добавьте элемент **\<system.webServer\>**, указывающий модуль для федеративной проверки подлинности.  Обратите внимание, что атрибут *PublicKeyToken* должен быть тем же, что и атрибут *PublicKeyToken* для записей **\<configSections\>**, добавленный ранее.  
  
    ```  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Добавьте следующие записи конфигурации идентификатора Windows, связанных учредительством и убедитесь, что URL\-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris\>**, атрибуте **область** элемента **\<wsFederation\>** и атрибуте **ответ** элемента **\<wsFederation\>**.  Также убедитесь в том, что значение **Поставщик** соответствия в URL\-адрес службы маркеров безопасности \(sts\).  
  
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
  
6.  Добавьте ссылку на сборку [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True).  
  
7.  Компилирование решение, чтобы убедиться, что ошибки.  
  
## Шаг 3 \- теста решение  
 На этом этапе тестировании для настроенного приложения веб\-форм ASP.NET для проверки подлинности на основе утверждений.  Выполнение простой тест, необходимо добавить код, который показывает утверждения в токене выданного службой маркеров безопасности \(sts\).  
  
#### Чтобы тестирование устройств формы приложение ASP.NET для проверки подлинности на основе утверждений  
  
1.  Откройте файл **Default.aspx** под проектом **TestApp** и замените его существующие разметка следующей разметкой:  
  
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
  
2.  Сохраните **Default.aspx**, а затем открыть его код, **Default.aspx.cs** именем файла.  
  
    > [!NOTE]
    >  **Default.aspx.cs** может быть скрыто в **Default.aspx** в обозревателе решений.  Если **Default.aspx.cs** не отображается, разверните **Default.aspx**, щелкнув треугольнике рядом с ним.  
  
3.  Замените существующий код в методе **Page\_Load** **Default.aspx.cs** следующим кодом:  
  
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
  
4.  Сохраните и выполните построение решения **Default.aspx.cs**.  
  
5.  Запустите решение, нажав клавиши ключ **F5**.  
  
6.  Необходимо со страницей, показывающая утверждения в токене, который был выдан возможность службой маркеров безопасности.