---
title: Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e8dc6b1c5073ac55be224eb0d410ad7f87d135d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a>Практическое руководство. Создание приложения ASP.NET Web Forms, поддерживающего утверждения, с помощью WIF
## <a name="applies-to"></a>Применение  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Веб-формы ASP.NET®  
  
## <a name="summary"></a>Сводка  
 В этом практическом руководстве представлены подробные пошаговые процедуры по созданию простого приложения веб-форм ASP.NET с поддержкой утверждений. Также здесь приводятся инструкции по тестированию простого приложения веб-форм ASP.NET с поддержкой утверждений для реализации федеративной проверки подлинности. В этом практическом руководстве не приводятся подробные инструкции по созданию службы маркеров безопасности (STS) и подразумевается, что вы уже выполнили ее настройку.  
  
## <a name="contents"></a>Описание  
  
-   Цели  
  
-   Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Шаг 3. Тестирование решения  
  
## <a name="objectives"></a>Цели  
  
-   Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений  
  
-   Тестирование приложения веб-форм ASP.NET с поддержкой утверждений  
  
## <a name="summary-of-steps"></a>Сводка действий  
  
-   Шаг 1. Создание простого приложения веб-форм ASP.NET  
  
-   Шаг 2. Настройка приложения веб-форм ASP.NET для федеративной проверки подлинности  
  
-   Шаг 3. Тестирование решения  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Шаг 1. Создание простого приложения веб-форм ASP.NET  
 На этом шаге создается новое приложение веб-форм ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Создание простого приложения ASP.NET  
  
1.  Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.  
  
2.  В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.  
  
3.  В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a>Шаг 2. Настройка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений  
 На этом шаге в файл конфигурации *Web.config* приложения веб-форм ASP.NET добавляются записи конфигурации, позволяющие реализовать поддержку утверждений.  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a>Настройка приложения ASP.NET для проверки подлинности на основе утверждений  
  
1.  Добавьте в файл конфигурации *Web.config* следующий раздел конфигурации непосредственно после открывающего элемента **\<configuration>**:  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Добавьте элемент **\<location>**, который обеспечивает доступ к метаданным федерации приложения:  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  Добавьте следующие записи конфигурации в элементы **\<system.web>**, чтобы запретить пользователей, отключить собственную проверку подлинности и включить платформу WIF для управления проверкой подлинности.  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Добавьте элемент **\<system.webServer>**, который определяет модули для федеративной проверки подлинности. Обратите внимание, что атрибут *PublicKeyToken* должен иметь то же значение, что и атрибут *PublicKeyToken* для ранее добавленных записей **\<configSections>**:  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Добавьте следующие записи конфигурации платформы Windows Identity Foundation и убедитесь, что URL-адрес и номер порта приложения ASP.NET соответствуют значениям в записи **\<audienceUris>**, атрибуте **realm** элемента **\<wsFederation>** и атрибуте **reply** элемента **\<wsFederation>**. Также убедитесь, что значение **issuer** соответствует URL-адресу службы маркеров безопасности (STS).  
  
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
  
6.  Добавьте ссылку на сборку <xref:System.IdentityModel>.  
  
7.  Скомпилируйте решение и убедитесь в отсутствии ошибок.  
  
## <a name="step-3--test-your-solution"></a>Шаг 3. Тестирование решения  
 На этом шаге выполняется тестирование приложения веб-форм ASP.NET, настроенного для проверки подлинности на основе утверждений. Для базовой проверки необходимо добавить код, который отображает утверждения в маркере безопасности, выданном службой STS.  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a>Проверка приложения веб-форм ASP.NET для проверки подлинности на основе утверждений  
  
1.  Откройте файл **Default.aspx** в проекте **TestApp** и замените существующую разметку следующей:  
  
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
  
2.  Сохраните файл **Default.aspx**, а затем откройте его файл кода программной части с именем **Default.aspx.cs**.  
  
    > [!NOTE]
    >  Файл **Default.aspx.cs** может быть скрыт в узле **Default.aspx** в обозревателе решений. Если файл **Default.aspx.cs** не отображается, разверните узел **Default.aspx**, щелкнув значок треугольника рядом с ним.  
  
3.  Замените существующий код метода **Page_Load** в файле **Default.aspx.cs** следующим:  
  
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
  
4.  Сохраните файл **Default.aspx.cs** и выполните построение решения.  
  
5.  Запустите решение, нажав клавишу **F5**.  
  
6.  Появится страница, на которой будут отображены утверждения в маркере безопасности, выданном службой маркеров безопасности.
