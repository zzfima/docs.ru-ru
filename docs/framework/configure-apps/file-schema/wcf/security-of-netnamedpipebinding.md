---
title: "&lt;security&gt; для &lt;netNamedPipeBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# &lt;security&gt; для &lt;netNamedPipeBinding&gt;
Определяет параметры безопасности для привязки.  
  
## Синтаксис  
  
```  
  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|Задает тип системы безопасности, применяемой к этой привязке.  Допустимы следующие значения:<br /><br /> -   None: режим безопасности отключен.<br />-   Transport: безопасность обеспечивается с помощью базовых функций безопасности транспорта.  Этот режим позволяет контролировать уровень защиты.<br />-   Значение по умолчанию \- Transport.  Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|транспорт|Определяет параметры безопасности для данного транспорта.  Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|привязка|Элемент привязки [\<netNamedPipeBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.NetNamedPipeSecurity>   
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Выбор типа учетных данных](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)