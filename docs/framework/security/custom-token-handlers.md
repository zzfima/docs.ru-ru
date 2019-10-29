---
title: Пользовательские обработчики маркеров
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: ccf794b4c229bbc9b40ae7ec2fd649825122cecf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040558"
---
# <a name="custom-token-handlers"></a>Пользовательские обработчики маркеров
В этом разделе описываются обработчики маркеров на платформе WIF и рассказывается о том, как использовать их для обработки маркеров. Кроме того, здесь рассматривается, что необходимо для создания пользовательских обработчиков для типов маркеров, которые по умолчанию не поддерживаются на платформе WIF.  
  
## <a name="introduction-to-token-handlers-in-wif"></a>Общие сведения об обработчиках маркеров на платформе WIF  
 На платформе WIF предусмотрены обработчики маркеров безопасности, которые используются для создания, чтения, записи и проверки маркеров для приложения проверяющей стороны и службы маркеров безопасности. Обработчики маркеров — это точки расширения, в которых вы можете добавлять на конвейер WIF пользовательские обработчики или настраивать поведение существующих обработчиков. На платформе WIF представлено девять встроенных обработчиков маркеров безопасности, которые при необходимости можно изменить или полностью переопределить.  
  
## <a name="built-in-security-token-handlers-in-wif"></a>Встроенные обработчики маркеров безопасности на платформе WIF  
 На платформе WIF 4.5 представлено девять классов для обработчиков маркеров безопасности, которые являются производными от абстрактного базового класса <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:  
  
- <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a>Добавление пользовательского обработчика маркеров  
 Для маркеров некоторых типов, таких как простые веб-маркеры (SWT) и веб-маркеры JSON (JWT), на платформе WIF не предусмотрены встроенные обработчики. Для таких маркеров и других маркеров, для которых отсутствует встроенный обработчик, необходимо создать пользовательский обработчик, выполнив следующие действия.  
  
#### <a name="adding-a-custom-token-handler"></a>Добавление пользовательского обработчика маркеров  
  
1. Создайте новый класс, производный от <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2. Переопределите следующие методы и предоставьте их собственную реализацию:  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3. Добавьте ссылку на новый пользовательский обработчик маркеров в файл *Web.config* или *App.config* в разделе **\<system.identityModel>** , который определяет параметры платформы WIF. Например, следующая разметка конфигурации задает новый обработчик маркеров **MyCustomTokenHandler**, который размещается в пространстве имен **CustomToken**.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Обратите внимание, что при определении собственного обработчика маркеров для типов маркеров со встроенным обработчиком необходимо добавить **элемент \<remove>** , чтобы исключить обработчик по умолчанию и использовать вместо него собственный. Например, в следующей конфигурации <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> заменяется пользовательским обработчиком маркеров:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789" />  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
