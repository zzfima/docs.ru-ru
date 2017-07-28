---
title: "&lt;securityTokenHandlers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;securityTokenHandlers&gt;
Указывает коллекции обработчиков маркеров безопасности, которые зарегистрированы с конечной точкой.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Имя коллекции обработчик маркеров.  Только значения, распознаваемые средой, «ActAs» и «OnBehalfOf».  Если с одним из этих имен коллекций обработчик маркеров, коллекция будет использоваться при обработке ActAs или OnBehalfOf маркеры соответственно.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет в коллекцию обработчиков маркеров обработчик маркеров безопасности.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Удаляет все обработчики маркеров безопасности из коллекции обработчиков маркеров.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Удаляет из коллекции обработчиков маркеров обработчик маркеров безопасности.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции обработчиков маркеров.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры уровня службы удостоверений.|  
  
## Заметки  
 В конфигурации службы можно указать один или несколько именованных семейств обработчики маркеров безопасности.  Можно указать имя коллекции с помощью `name` атрибут.  Только имена, которые обрабатывает платформы, «ActAs» и «OnBehalfOf».  Если в эти коллекции обработчиков, они используются службы маркеров безопасности \(STS\) вместо обработчиков по умолчанию при обработке `ActAs` и `OnBehalfOf` маркеры.  
  
 По умолчанию коллекция заполняется со следующими типами обработчика: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.  Коллекцию можно изменить с помощью `<add>`, `<remove>`, и `<clear>` элементов.  Необходимо обеспечить наличие одного обработчика для определенного типа в коллекции.  Например, если производные обработчик из <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса либо обработчик или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> может быть настроен в одной коллекции, но не оба.  
  
 Использование `<securityTokenHandlerConfiguration>` элемента необходимо указать параметры конфигурации для обработчиков в коллекции.  Переопределять параметры, указанные с помощью данного элемента, указанные службы с помощью [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.  Некоторые обработчики \(включая некоторые типы встроенных обработчиков\) может поддерживать дополнительные конфигурации через дочерний элемент `<add>` элемент.  Параметры, заданные на обработчик переопределения эквивалентных параметров, указанных в коллекции или службы.