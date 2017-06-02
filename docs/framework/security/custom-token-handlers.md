---
title: "Обработчики пользовательских токенов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Обработчики пользовательских токенов
В этом разделе рассматриваются обработчики токена в WIF и их используется для обработки токены.  В этом разделе также описывается, что необходимо для создания пользовательских обработчиков токена для типов токена, не поддерживаемого по умолчанию в WIF.  
  
## Знакомство с обработчикам токена в WIF  
 WIF зависит от обработчиков маркеров безопасности для создания, чтения, записи и проверить токены для приложения проверяющей стороны \(проверяющая сторона использует версию\) или службой маркеров безопасности \(sts\).  Обработчики токена точки расширяемости для добавления обработчика пользовательского токена в конвейере WIF или настраивать способ существующий обработчик токена управляет токены.  WIF содержит 9 встроенных обработчиков маркеров безопасности, которые могут быть изменены или полностью переопределять, чтобы изменить функциональность по мере необходимости.  
  
## Встроенные обработчики маркеров безопасности в WIF  
 WIF 4,5 включает 9 классов обработчика маркеров безопасности, наследуемых от абстрактного базового класса <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## Добавление обработчика пользовательского токена  
 Некоторые типы токена, как простые токены маркеров Интернета \(SWT\) и интернет JSON \(JWT\) не имеют встроенных обработчиков токена, доступные в WIF.  Для этих типов токена и для других, которые не имеют встроенной обработчик, необходимо выполнить следующие шаги для создания обработчика пользовательского токена.  
  
#### Добавление обработчика пользовательского токена  
  
1.  Создайте новый класс, производный от <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2.  Переопределить следующие методы и предоставить собственную реализацию:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  Добавьте ссылку на новый пользовательский обработчик токена в *Web.config или* App.configfile *,* в разделе **\<system.identityModel\>**, который применяется к WIF.  Например, в следующей разметке конфигурации определяют новый обработчик с именем токена **MyCustomTokenHandler**, который находится в пространстве имен **CustomToken**.  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Обратите внимание, что если указать собственный обработчик токена для обработки тип токена, который уже имеет встроенный механизм токена, необходимо добавить элемент **\<remove\>** для удаления по умолчанию и использовать обработчик пользовательского обработчика.  Например, следующая конфигурация заменяет используемые по умолчанию <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> с настраиваемым обработчиком токена:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type=”System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789”>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```