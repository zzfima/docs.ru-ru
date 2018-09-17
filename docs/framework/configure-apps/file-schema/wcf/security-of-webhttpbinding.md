---
title: '&lt;security&gt; для &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 52146fa08ec63ef63fa996cdc09f9185b9f42e02
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698514"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a>&lt;security&gt; для &lt;webHttpBinding&gt;
Задает требования к безопасности для конечной точки, настроенной с [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 \<система. ServiceModel >  
\<привязки >  
\<webHttpBinding >  
\<Привязка >  
\<Безопасность >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|режим|Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется. Значение по умолчанию — `None`. Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Атрибут mode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Режим безопасности отключен.|  
|Transport|Безопасность обеспечивается с помощью протокола HTTPS. Необходимо настроить службу с использованием сертификата SSL. Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы. Проверка подлинности клиента контролируется посредством `ClientCredentialType` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Данный режим не обеспечивает целостности и конфиденциальности сообщений. Он обеспечивает проверку подлинности клиента на основе HTTP. Этот режим следует использовать с осторожностью. Он должен использоваться в средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а только проверку подлинности клиента с помощью инфраструктуры WCF.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Транспорт >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|Определяет параметры безопасности транспорта. Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Элемент привязки, который используется для настройки конечных точек для Windows Communication Foundation (WCF) веб-служб, которые отвечают на запросы HTTP вместо сообщений SOAP.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Выбор типа учетных данных](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки службы Windows Communication Foundation и клиентов](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)  
 [Модель веб-программирования HTTP WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
