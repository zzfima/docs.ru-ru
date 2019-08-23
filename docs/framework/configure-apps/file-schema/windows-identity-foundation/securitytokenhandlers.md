---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942461"
---
# <a name="securitytokenhandlers"></a>\<securityTokenHandlers >
Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.  
  
 \<> System. identityModel  
\<identityConfiguration >  
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
|имя|Указывает имя коллекции обработчиков маркеров. Платформа принимает только те значения, которые распознаются платформой: "ActAs" и "OnBehalfOf". Если коллекции обработчиков маркеров указаны с одним из этих имен, коллекция будет использоваться при обработке маркеров ActAs или OnBehalfOf соответственно.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add.md)|Добавляет обработчик маркеров безопасности в коллекцию обработчиков маркеров.|  
|[\<clear>](clear.md)|Удаляет все обработчики маркеров безопасности из коллекции обработчиков маркеров.|  
|[\<remove>](remove.md)|Удаляет обработчик маркера безопасности из коллекции обработчиков маркеров.|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
  
## <a name="remarks"></a>Примечания  
 В конфигурации службы можно указать одну или несколько именованных коллекций обработчиков маркеров безопасности. Имя коллекции можно указать с помощью `name` атрибута. Единственными именами, которые обрабатывает платформа, являются "ActAs" и "OnBehalfOf". Если в этих коллекциях есть обработчики, они используются службой маркеров безопасности (STS) вместо обработчиков по умолчанию при обработке `ActAs` и `OnBehalfOf` токенах.  
  
 По умолчанию <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>коллекция заполняется следующими типами обработчиков:, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. Коллекцию можно изменить с помощью `<add>`элементов, `<remove>`и `<clear>` . Необходимо убедиться, что в коллекции существует только один обработчик любого определенного типа. Например, если создать производный обработчик от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, то либо обработчик, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> либо может быть настроен в одной коллекции, но не в обоих.  
  
 Используйте элемент `<securityTokenHandlerConfiguration>` , чтобы указать параметры конфигурации для обработчиков в коллекции. Параметры, заданные с помощью этого элемента, [ \<](identityconfiguration.md) переопределяют указанные в службе элементы с помощью элемента identityConfiguration >. Некоторые обработчики (включая несколько встроенных типов обработчиков) могут поддерживать дополнительную конфигурацию через дочерний элемент `<add>` элемента. Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции или службе.
