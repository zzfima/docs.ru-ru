---
title: "&lt;security&gt; для &lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;security&gt; для &lt;webHttpBinding&gt;
Определяет требования безопасности для конечной точки, настроенной с помощью элемента [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
## Синтаксис  
  
```  
  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.  Значение по умолчанию — `None`.  Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## Атрибут mode  
  
|Значение|Описание|  
|--------------|--------------|  
|Нет|Режим безопасности отключен.|  
|Transport|Безопасность обеспечивается с помощью протокола HTTPS.  Необходимо настроить службу с использованием сертификата SSL.  Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL\-сертификата службы.  Проверка подлинности клиента управляется посредством атрибута `ClientCredentialType` элемента [\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Данный режим не обеспечивает целостности и конфиденциальности сообщений.  Он обеспечивает проверку подлинности клиента на основе HTTP.  Этот режим следует использовать с осторожностью.  Он должен использоваться в тех средах, где безопасность транспорта обеспечивается другими средствами \(например, IPSec\), а инфраструктура [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] обеспечивает только проверку подлинности клиента.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|Определяет параметры безопасности транспорта.  Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Элемент привязки, который используется при настройке конечных точек для веб\-служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые отвечают на запросы HTTP вместо сообщений SOAP.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.WebHttpSecurity>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Выбор типа учетных данных](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)   
 [Модель веб\-программирования HTTP WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)