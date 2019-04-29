---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: a5af3893ab72d23c2b3814569decfc50431b8e55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793839"
---
# <a name="securitytokenhandlers"></a>\<securityTokenHandlers >
Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Указывает имя коллекции обработчиков токенов. Только значения, распознаются платформой являются «ActAs» и «OnBehalfOf». Если с любой из этих имен указаны коллекции обработчиков токенов, коллекции будет использоваться при обработке ActAs или OnBehalfOf маркеров соответственно.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Удаляет все обработчики маркеров безопасности из коллекции обработчиков токенов.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Удаляет обработчик токенов безопасности из коллекции обработчиков токенов.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков токенов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы идентификации.|  
  
## <a name="remarks"></a>Примечания  
 В конфигурации службы можно указать одну или несколько именованных коллекций обработчиков токенов безопасности. Можно указать имя для коллекции с помощью `name` атрибута. Это единственные имена, платформа обрабатывает являются «ActAs» и «OnBehalfOf». Если в эти коллекции существуют обработчики, они используются службой маркеров безопасности (STS) вместо обработчики по умолчанию при обработке `ActAs` и `OnBehalfOf` маркеров.  
  
 По умолчанию коллекция заполняется следующие типы обработчиков: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. Коллекции можно изменить с помощью `<add>`, `<remove>`, и `<clear>` элементов. Необходимо убедиться, что только один обработчик любого конкретного типа существует в коллекции. Например, если вы наследуете обработчика <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, либо обработчик или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> могут быть настроены в одной коллекции, но не оба.  
  
 Используйте `<securityTokenHandlerConfiguration>` элемента, чтобы указать параметры конфигурации для обработчиков в коллекции. Параметры, заданные с помощью этого элемента переопределяют указанные службы с помощью [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент. Некоторые обработчики (включая некоторых типов встроенный обработчик) может поддерживать дополнительные конфигурации через дочерний элемент элемента `<add>` элемент. Настройки, указанные на обработчик переопределяют аналогичные параметры, заданные в коллекции или службы.
