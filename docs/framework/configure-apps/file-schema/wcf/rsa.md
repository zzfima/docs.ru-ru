---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714036b6f7cb64fd12cd48eabb4203279431e5a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltrsagt"></a>&lt;RSA&gt;
Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.  
  
 \<удостоверение >  
\<RSA >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|value|Дополнительная строка. Значение открытого ключа RSA, с которым происходит сравнение на клиенте.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="remarks"></a>Примечания  
 Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке. Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.  
  
 Дополнительные сведения об использовании идентификаторов для проверки службы для клиента см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="example"></a>Пример  
 В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [Службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
